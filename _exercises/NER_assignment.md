---
layout: page
title: NER Assignment
description: Named Entity Recognition Assignment
---

# NER Assignment
Georeferencing automatically detected place names in Edward Gibbon's *Decline and Fall of the Roman Empire* using the Pleiades gazatteer and `spaCy`.

Your assignment this week is to output a `CSV` file of place names, frequency and coordinates, as we did in class for a chapter of Gibbon of your choice. Try to find a chapter with a lot of places as we will be turning this data into an online map next week. The steps are:

* Choose a chapter from the text
* Begin a function by parsing input text
* Create a `spaCy` dictionary of entities and frequency
* Use the Pleiaes data from class to find coordinates for each place name
* Run your function on your chosen chapter
* Save your final `CSV`
* Come to class on Monday, ready to use it


```python
# import and download any relevant data
import wget
import spacy
from collections import defaultdict
import pandas as pd
import os

nlp = spacy.load('en_core_web_sm')

if not os.path.isfile('places.csv'):
    wget.download('https://raw.githubusercontent.com/pnadelofficial/FallDHCourseMaterials/main/places.csv')
if not os.path.isfile('names.csv'):
    wget.download('https://raw.githubusercontent.com/pnadelofficial/FallDHCourseMaterials/main/names.csv')
if not os.path.isfile('gibbon_text.csv'):
    wget.download('https://raw.githubusercontent.com/pnadelofficial/FallDHCourseMaterials/main/gibbon_text.csv')

gibbon_by_chapter = pd.read_csv('gibbon_text.csv').rename(columns={'Unnamed: 0':'chapter'})
names = pd.read_csv('names.csv')
places = pd.read_csv('places.csv')
```


```python
# any helper functions you may need

def get_pleiades_id(term):
    name_row = names.loc[names['attested_form'] == term]
    if len(name_row) == 1:
        return int(name_row.place_id.iloc[0])
    else:
        name_row = names.loc[names['romanized_form_1'] == term]
        if len(name_row) == 1:
            return int(name_row.place_id.iloc[0])
        else:
            name_row = names.loc[names['romanized_form_2'] == term]
            if len(name_row) == 1:
                return int(name_row.place_id.iloc[0])
            else:
                name_row = names.loc[names['romanized_form_3'] == term]
                if len(name_row) == 1:
                    return int(name_row.place_id.iloc[0])
                else:
                    return None

def get_lat(pl_id):
    places_row = places.loc[places['id'] == pl_id]
    if len(places_row) == 1:
        return places_row.representative_latitude.iloc[0]
    
def get_long(pl_id):
    places_row = places.loc[places['id'] == pl_id]
    if len(places_row) == 1:
        return places_row.representative_longitude.iloc[0]

```


```python
# final functions
def get_place_frequency(chapter, data):
    chapter_data = data['StringText'][chapter]
    chapter_nlp = nlp(chapter_data)
    place_freq = defaultdict(int)
    for entity in chapter_nlp.ents:
        if (entity.label_ == 'GPE') or (entity.label_ == 'LOC'):
            place_freq[entity.text] += 1
    place_freq = dict(place_freq)
    place_freq_df = pd.DataFrame.from_dict(place_freq, orient='index').reset_index().rename(columns={'index': 'place_name',0: 'frequency'})
    place_freq_df['pleiades_id'] = place_freq_df['place_name'].apply(get_pleiades_id)
    place_freq_final = place_freq_df.dropna().reset_index(drop=True)
    place_freq_final['lat'] = place_freq_final['pleiades_id'].apply(get_lat)
    place_freq_final['long'] = place_freq_final['pleiades_id'].apply(get_long)
    
    return place_freq_final
```


```python
# try your function out
freq = get_place_frequency(11, gibbon_by_chapter)
print(freq)
```

          place_name  frequency  pleiades_id        lat       long
    0           Rome         23     423025.0  41.891775  12.486137
    1         Africa          5        775.0  32.500000   7.500000
    2          Milan          1     383706.0  45.463746   9.188060
    3   Thessalonica          1     491741.0  40.628342  22.952885
    4        Corinth          1     570182.0  37.906329  22.880841
    5         Athens          2     579885.0  37.972634  23.722746
    6        Maeotis          1     825318.0  46.072677  36.711669
    7         Pontus          1     857287.0  43.078685  34.742551
    8      Illyricum          3     481865.0  42.427292  17.965028
    9           Nile          3     727172.0  19.211409  30.567330
    10        Coptos          1     786010.0  25.996402  32.815787
    11      Hercules          1     266032.0  37.500000  -0.500000
    12       Sirmium          1     207447.0  44.966447  19.610106
    13         India          1      50004.0  22.500000  77.500000
    14        Arabia          1     981506.0  27.500000  32.500000
    15     Chalcedon          2     520988.0  40.983393  29.025789
    16      Heraclea          1     452333.0  40.211776  16.669885



```python
# save result as CSV
freq.to_csv('gibbon_places_chapter11.csv')
```
