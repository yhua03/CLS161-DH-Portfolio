---
layout: page
title: Downloading Web Pages with Python
description: This lesson introduces Uniform Resource Locators (URLs) and explains how to use Python to download and save the contents of a web page to your local hard drive.
---
## Source
[Downloading Web Pages with Python(https://doi.org/10.46430/phen0021)]
(https://programminghistorian.org/en/lessons/working-with-web-pages)


## Reflection

I've taken COMP20 before where I learned a little bit about front-end programming languages. I wanted to take this opportunity to explore how is Python applied and being used in web programming, thus, I found this Programming Historian Lesson that covers a very specific topic of web programming: URL. This lesson did a very effective job explaining what URLs are and how is Python related to the topic. Although the task "downloading web pages" might not be as practical or sound as important as some of the other Python applications, I believe it is a fundamental step of Python programming in front-end coding. 

After reading through the lesson tutorials, I decided to change up the content a little bit and try downloading my own URL and web pages through the application and coding content the lesson covers, which can be shown below in the Code Section:


## Code: Opening Web Pages With Python
```python
import urllib.request, urllib.error, urllib.parse

url = 'https://www.op.gg/'

response = urllib.request.urlopen(url)
webContent = response.read().decode('UTF-8')

print(webContent[0:300])
```
