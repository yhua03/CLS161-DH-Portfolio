---
layout: page
title: Chronicling America API
description: Using the Chronicling America API to query for a keyword, parse the result, and save it to a csv file
---

## Chronicling America API Assignment
In this assignment, you are tasked with:
* searching Chronicling America's API for a key word of your choice
* parsing your results from a dictionary to a `DataFrame` with headings "title", "city", 'date", and "raw_text"
* processing the raw text by removing "\n" characters, stopwords, and then lemmatizing the raw text before adding it to a new column called "lemmas."
* saving your `DataFrame` to a csv file


```python
# imports
import requests
import json
import math
import pandas as pd
import spacy
```


```python
# initial search: search for 'soccer'
url = 'https://chroniclingamerica.loc.gov/search/pages/results/?state=&date1=1821&date2=1963&proxtext=soccer&x=8&y=14&dateFilterType=yearRange&rows=20&searchType=basic&format=json'
results = json.loads(requests.get(url).text)
```


```python
# find total amount of pages
total_pages = math.ceil(results['totalItems'] / results['itemsPerPage'])
print(total_pages)
```

    2747



```python
# query the api and save to dict 
from time import sleep
data = []
start_date = '1821'
end_date = '1963'
search_term = 'soccer'
for i in range(1, total_pages + 1):
    url = (f'https://chroniclingamerica.loc.gov/search/pages/results/?state=&date1={start_date}'
           f'&date2={end_date}&proxtext={search_term}&x=8&y=14&dateFilterType=yearRange&rows=20'
           f'&searchType=basic&format=json&page={i}')
    sleep(0.20)
    response = requests.get(url)
    raw = response.text
    if response.status_code != 200: continue
    # Note: I have noticed that sending too many requests sends a 503 error, so for the sake of this assignment I skip over responses that result in errors
    # To make this more robust, a sleep timeout can be added between each request to prevent our queries from getting rate-limited (like sleep(0.20) above)
    results = json.loads(raw)
    items = results['items']
    for item in items:
        data_dict = dict()
        if 'title_normal' in item and 'city' in item and 'date' in item and 'ocr_eng' in item:
            data_dict['title'] = item['title_normal']
            data_dict['city'] = item['city']
            data_dict['date'] = item['date']
            data_dict['raw_text'] = item['ocr_eng']
            data.append(data_dict)
```


```python
# convert dict to dataframe
df = pd.DataFrame.from_dict(data)
df.head() # just checking... :p
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>city</th>
      <th>date</th>
      <th>raw_text</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>0</th>
      <td>evening star.</td>
      <td>[Washington]</td>
      <td>19580323</td>
      <td>shop early. shop Imlr. Monday both «lor«*«\nUa...</td>
    </tr>
    <tr>
      <th>1</th>
      <td>evening star.</td>
      <td>[Washington]</td>
      <td>19191026</td>
      <td>War Workers at Play\nClark Griffith, manager o...</td>
    </tr>
    <tr>
      <th>2</th>
      <td>evening star.</td>
      <td>[Washington]</td>
      <td>19580323</td>
      <td>- . , :v :;vV\nRlßjrlt i .(v I jSfetlr ' 4 *■\...</td>
    </tr>
    <tr>
      <th>3</th>
      <td>ogden standard.</td>
      <td>[Ogden]</td>
      <td>19180928</td>
      <td>I - THE OGDEN STANDARD, ' ; f - jL a\nI Soccer...</td>
    </tr>
    <tr>
      <th>4</th>
      <td>day book.</td>
      <td>[Chicago]</td>
      <td>19170316</td>
      <td>BILLY SUNDAY TABERNACLE IN NEW YORK\nWhile Bil...</td>
    </tr>
  </tbody>
</table>
</div>




```python
# convert date column from string to date-time object
df['date'] = pd.to_datetime(df['date'])
```


```python
# sort by date
sorted_df = df.sort_values(by='date')
```


```python
# write fuction to process text
nlp = spacy.load("en_core_web_sm")
nlp.disable_pipes('ner', 'parser')

# source: Prof. Saxton's notebook from class
def process_text(text):
    """Remove new line characters and lemmatize text. Returns string of lemmas"""
    text = text.replace('\n', ' ')
    doc = nlp(text)
    tokens = [token for token in doc]
    no_stops = [token for token in tokens if not token.is_stop]
    no_punct = [token for token in no_stops if token.is_alpha]
    lemmas = [token.lemma_ for token in no_punct]
    lemmas_lower = [lemma.lower() for lemma in lemmas]
    lemmas_string = ' '.join(lemmas_lower)
    return lemmas_string

```


```python
# apply process_text function to raw_text column
sorted_df['lemmas'] = sorted_df['raw_text'].apply(process_text)
sorted_df.head() # checking the output
```




<div>
<style scoped>
    .dataframe tbody tr th:only-of-type {
        vertical-align: middle;
    }

    .dataframe tbody tr th {
        vertical-align: top;
    }

    .dataframe thead th {
        text-align: right;
    }
</style>
<table border="1" class="dataframe">
  <thead>
    <tr style="text-align: right;">
      <th></th>
      <th>title</th>
      <th>city</th>
      <th>date</th>
      <th>raw_text</th>
      <th>lemmas</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <th>7115</th>
      <td>lamar register.</td>
      <td>[Lamar]</td>
      <td>1897-07-03</td>
      <td>THE LAMAR REGISTER.\nKntorai at tli* Pintofttc...</td>
      <td>lamar register kntorai tli pintofttc lamar col...</td>
    </tr>
    <tr>
      <th>3426</th>
      <td>times.</td>
      <td>[Richmond]</td>
      <td>1899-04-20</td>
      <td>WILL CO-OPERATE\nWITH AMERICANS\nG . * r\ i Su...</td>
      <td>co operate american g support amer s agitation...</td>
    </tr>
    <tr>
      <th>4439</th>
      <td>daily morning journal and courier.</td>
      <td>[New Haven]</td>
      <td>1899-09-14</td>
      <td>10\nTHIS CENTURY'S PROGRESSf\nGREAT C0MPAUF.D ...</td>
      <td>century progressf great vlletiovs timk preside...</td>
    </tr>
    <tr>
      <th>4554</th>
      <td>morning news.</td>
      <td>[Savannah]</td>
      <td>1899-09-17</td>
      <td>12\nThe monotony of the last week was un\nbrok...</td>
      <td>monotony week un break excitement kind hard re...</td>
    </tr>
    <tr>
      <th>6566</th>
      <td>times.</td>
      <td>[Washington]</td>
      <td>1899-09-21</td>
      <td>THE TIMES, WASHINGTON, THURSDAY, SEPTEMBER 21....</td>
      <td>times washington thursday september lansburgh ...</td>
    </tr>
  </tbody>
</table>
</div>




```python
# save to csv
sorted_df.to_csv(f'../assets/{search_term}{start_date}-{end_date}.csv', index=False)

# note: the file is too large to be uploaded to github, so I hosted it myself. It can be found at:

```
