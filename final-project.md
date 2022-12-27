---
layout: page
title: Final Project
permalink: /final-project/
---


The final project that I decided to do was to analyze and better understand the speech frequencies and trending topics among the gaming communities. To gather the data that I needed for the research, I chose Reddit as the discussion forum that I wanted to collect data from because there are plenty of existing APIs and Python Libraries that contain functions that allow me to directly access the Reddit database.

The appraoch that I decided to take was to choose several channels, each of which represents one of the most popular games today. I chose five games for the research project, and each of which is its unique genre, ranging from multiplayer online battle arena (MOBA) to first-person shooting game(FPS). The games that I chose are : League of Legends, Apex Legends, Teamfight Tactics, Valorant, and Call of Duty. I will introduce each of the game below with statistics to show its relevance to the society, especially the younger generation.

**Leauge of Legends**

League of Legends (LoL) is a multiplayer online battle arena (MOBA) video game developed and published by Riot Games. It is one of the most popular games in the world, with millions of active players and a dedicated competitive scene. In LoL, players control a champion character and work with their team to destroy the enemy team's nexus, which is located in the enemy team's base. Each champion has unique abilities and characteristics, and players can earn experience points and gold by defeating enemy champions and minions (computer-controlled characters that fight for each team). Players can use the gold they earn to purchase items that can improve their champion's stats and abilities.

It is difficult to determine the exact number of active players in League of Legends (LoL) at any given time, as the game has a large and constantly changing player base. However, Riot Games, the developer and publisher of LoL, has reported that the game has an average of around 8 million daily players and a peak of around 11 million concurrent players. These numbers have likely changed since my knowledge cutoff in 2021, and it is possible that the game has even more active players now. LoL is one of the most popular games in the world and has a dedicated player base and competitive scene.


**Teamfight Tactics**

Teamfight Tactics (TFT) is a strategy game developed and published by Riot Games, the same company that developed League of Legends (LoL). TFT is a round-based strategy game that is played on a grid-based board. Players start each round with a set amount of gold and use it to recruit champions and build a team. The game has elements of deck-building and dice rolling, as players can purchase and upgrade items for their champions and roll for random effects on the board. TFT has been very popular since its release and has a dedicated player base. It is possible that the game has millions of active players.

**Valorant**


``python

# -*- coding: utf-8 -*-
import pandas as pd
import wordcloud
import json
from matplotlib import pyplot as plt
plt.rcParams["font.serif"] = "cmr10"
``

**To define Game List**
``python
game_list = ['apex', 'cod', 'league', 'tft', 'valorant']
# game_list = ['apex']
``
