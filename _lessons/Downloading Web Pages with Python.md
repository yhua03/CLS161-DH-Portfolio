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

After reading through the lesson tutorials, I decided to change up the content a little bit and try downloading the sample URL and web pages through the application and coding content the lesson covers, which can be shown below in the Code Section:


## Code: Opening Web Pages With Python

```python
import urllib.request, urllib.error, urllib.parse

url = 'http://www.oldbaileyonline.org/browse.jsp?id=t17800628-33&div=t17800628-33'

response = urllib.request.urlopen(url)
webContent = response.read().decode('UTF-8')

print(webContent[0:300])
```

The five lines of code above contain three variables that I named, url, response and webContent. The variable url simply stores our desired url, and the response variable utilizes a function called urlopen, which is a part of the urllib.request that we imported initially. 

Below denotes the resulting output of the command lines, which contains some HTML markups: 
```python
<!DOCTYPE html PUBLIC "-//W3C//DTD XHTML 1.0 Strict//EN" "http://www.w3.org/TR/xhtml1/DTD/xhtml1-strict.dtd">
<html xmlns="http://www.w3.org/1999/xhtml" xml:lang="en" lang="en">
<head>
	<title>Browse - Central Criminal Court</title>
	<meta http-equiv="content-type" content=
```

## Code : Saving a Local Copy of A Web Pagee
The code below shows how to save a local copy of a web page to your own device. 
```python
import urllib.request, urllib.error, urllib.parse

url = 'ttp://www.oldbaileyonline.org/browse.jsp?id=t17800628-33&div=t17800628-33'

response = urllib.request.urlopen(url)
webContent = response.read().decode('UTF-8')

f = open('obo-t17800628-33.html', 'w')
f.write(webContent)
f.close
```

The string obo-t17800628-33.html is a verifier for the URL's unique id that I briefly mentioned in the beginning. Because the web page was written with JSP, it means that each page has a unique identifier that is part of the url shown after "id=".

## Next Steps
I think the next programming historian lesson that I will probably read and learn more about is "Downloading Multiple Records Using Query Strings", as it introduces a method to download files on a scale rather than manually once at a time. 
