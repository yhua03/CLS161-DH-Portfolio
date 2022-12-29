---
layout: page
title: Final Project
permalink: /final-project/
---


The final project that I decided to do was to analyze and better understand the speech frequencies and trending topics among the gaming communities. To gather the data that I needed for the research, I chose Reddit as the discussion forum that I wanted to collect data from because there are plenty of existing APIs and Python Libraries that contain functions that allow me to directly access the Reddit database.

The appraoch that I decided to take was to choose several channels, each of which represents one of the most popular games today. I chose five games for the research project, and each of which is its unique genre, ranging from multiplayer online battle arena (MOBA) to first-person shooting game(FPS). The games that I chose are : League of Legends, Apex Legends, Teamfight Tactics, Valorant, and Call of Duty. I will introduce each of the game below with statistics to show its relevance to the society, especially the younger generation.

**Leauge of Legends**

League of Legends (LoL) is a multiplayer online battle arena (MOBA) video game developed and published by Riot Games. It is one of the most popular games in the world, with millions of active players and a dedicated competitive scene. In LoL, players control a champion character and work with their team to destroy the enemy team's nexus, which is located in the enemy team's base. 

Riot Games has reported that the game has an average of around 8 million daily players and a peak of around **11 million** concurrent players.


**Teamfight Tactics**

Teamfight Tactics (TFT) is a strategy game developed and published by Riot Games, the same company that developed League of Legends (LoL). TFT is a round-based strategy game that is played on a grid-based board. TFT has been very popular since its release and has a dedicated player base. It is possible that the game has **millions** of active players.

**Valorant**

Valorant is another tactical first-person shooter (FPS) video game developed and published by Riot Games. It is set in a near-future Earth and features a cast of characters known as "Agents", each with their own unique set of weapons and abilities. The game combines tactical shooting with elements of battle royale and character-based shooter games The population of Valorant is estimated at about **16.43M** players.

**Apex Legends**

Apex Legends is a free-to-play battle royale game developed by Respawn Entertainment and published by Electronic Arts. It was released for Microsoft Windows, PlayStation 4, and Xbox One on February 4, 2019. The game is set in the Titanfall universe and features a cast of characters known as “Legends”. Each Legend has their own unique set of abilities and playstyles, allowing players to choose their favorite and create teams that synergize with one another. As of April 2020, Apex Legends has over **70 million** players worldwide.

**Call Of Duty**

Call of Duty is a first-person shooter video game franchise. Published by Activision, COD was first released in 2003, and has since become one of the most popular video game franchises of all time. The games are set in different time periods and feature a variety of game modes. As of April 2020, the Call of Duty franchise has over **250 million** players worldwide.



Imported Libraries and Initial setup: 


```python
import pandas as pd
import wordcloud
import json
from matplotlib import pyplot as plt
plt.rcParams["font.serif"] = "cmr10"
```

Defining Game Lists:


```python
game_list = ['apex', 'cod', 'league', 'tft', 'valorant']
game_list = ['apex']
```


Data Loading & Processing: 

```python
def process_dict(dict_list):
    text = ''
    
    while dict_list:
        cur_dict = dict_list.pop(0)
        
        cur_data = cur_dict['data']

        if 'body' in cur_data:
            text += cur_data['body'] + ' '
        
        if 'children' in cur_data:
            for child in cur_data['children']:
                if type(child) == dict:
                    dict_list.append(child)
    
    return text
    
text_dict = {}

for game in game_list:
    # read json file
    text = ''
    for i in range(1, 6):
        with open(f'./data/{game}/{i}.json', 'r') as f:
            data = json.load(f)
            text += process_dict(data)
    text_dict[game] = text
```

Data Analysis & Visualization:

```python
n = 20
stop_words = list(wordcloud.STOPWORDS)
stop_words.extend(['I', '', 'This', 'The', 'It', 'You', 'A', 'And', 'I\'m', 'That', 'If', 'much', 'got', 'game'])

def word_freq(text):
    word_list = text.split(' ')
    word_dict = {}
    for word in word_list:
        if word in word_dict:
            word_dict[word] += 1
        else:
            word_dict[word] = 1
    return word_dict

for game in game_list:
    word_dict = word_freq(text_dict[game])
    word_dict = sorted(word_dict.items(), key=lambda x: x[1], reverse=True)\
    
    # delete stop words from the word_dict
    no_stopword = filter(lambda x: x[0] not in stop_words, word_dict)
    word_dict = list(no_stopword)[:n]
    word_dict = dict(word_dict)

    # plot the top 20 words with pyplot
    plt.figure(figsize=(10, 5))
    plt.bar(word_dict.keys(), word_dict.values())
    plt.xticks(rotation=90)
    plt.title(f'{game} word frequency')
    plt.savefig(f'./result/{game}_word_freq.png')
 ```
 
For each of the gaming communities and channels, I chose the top 5 trending threads and used the code above to analyze the discussion content through the perspective of speech frequencies. Below are the results of the python analysis for each of the channel, displayed as a bar chart and as word clouds. The Y-coordinate of the chart is the number of times that certain word has appeared under the selected threads, and the X-coordinate represents the word/phrases.

**Word Frequencies Results**
 

<img src="../assets/apex_word_freq.png" width="800"/>

The most frequently appearing wrods under Apex Legend threads are Heirloom, make, see, people and one. A lot of the words are common transition words or verbs that does not have any unique connotation to the Apex Legends community. However, some words such as Heirloom is unique to Apex, as Heirlooms are Mythic-tier cosmetic items that change the skin of your melee weapon in Apex Legends.

<img src="../assets/cod_word_freq.png" width="800"/>

Interestingly, three of the most frequently appearing words under COD threads are blue, red and black. It seems that in the game of COD, the two teams playing against each other is represented in one of the two colors: blue or red. And since some of the past COD games are sold under the name Black Ops, that might explain the high frequencies of the word black as well. 

<img src="../assets/league_word_freq.png" width="800"/>

The most frequently appearing words under league of legends threads are even, hope, reall and Riot. I don't quite understand the connotation of even as it could be said as a transition word or as an adjective to show fairness, but it is intriguing that it's the most frequently appearing word. Also interestingly, it is odd that "hope" appears 14 times among discussions of League of Legends. Perhaps it is worth looking deeper into the actual content of the discussion to acquire a more accurate interpretation of these two words. Riot is an anticipated word that appears frequently, since the company behind League of Legends is called Riot Games. 


<img src="../assets/tft_word_freq.png" width="800"/>

For teamfight tactics, since the background of the game overlaps with League of Legends a lot, it is expected that some of the most frequently appearing words are common. For example, the word "even" is one of the most frequently appearing words here under TFT as well. Of course, there are multiple words on the list that are unique to the game, such as Yordles and Duo. 


<img src="../assets/valorant_word_freq.png" width="800"/>
 
```python
# wordcloud generation

# add more stopwords
stopwords = wordcloud.STOPWORDS
stopwords.add('game')

for game in game_list:
    wc = wordcloud.WordCloud(width=800, height=600, background_color='white', max_words=100, stopwords=stopwords)
    wc.generate(text_dict[game])
    wc.to_file(f'./result/{game}_wordcloud.png')
```
**

**Generated Word Cloud Images**

Below are the word cloud images that I've genegerated based on the previous word frequencies analysis using Python (as shown above in the code)
<img src="../assets/apex_wordcloud.png" width="800"/>

<img src="../assets/cod_wordcloud.png" width="800"/>

<img src="../assets/league_wordcloud.png" width="800"/>

<img src="../assets/tft_wordcloud.png" width="800"/>

<img src="../assets/valorant_wordcloud.png" width="800"/>
