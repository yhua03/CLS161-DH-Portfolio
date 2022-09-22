---
layout: page
title: Counting Word Frequencies with Python
description: This lesson uses Python to count word frequencies, which can be used in several ways to analyze texts.
---

## Source
[Turkel, W. J., & Crymble, A. (2012). Counting Word Frequencies with Python. _The Programming Historian_, 1. https://doi.org/10.46430/phen0003](https://programminghistorian.org/en/lessons/counting-frequencies)

## Reflection
TODO

## Code

### Counting Frequencies in a List
Before diving into counting word frequencies from a text file, we will first look at techniques to count word frequencies in a list.

```python
# count-list-items-1.py

wordstring = 'it was the best of times it was the worst of times '
wordstring += 'it was the age of wisdom it was the age of foolishness'

wordlist = wordstring.split()

wordfreq = []
for w in wordlist:
    wordfreq.append(wordlist.count(w))

print("String\n" + wordstring +"\n")
print("List\n" + str(wordlist) + "\n")
print("Frequencies\n" + str(wordfreq) + "\n")
print("Pairs\n" + str(list(zip(wordlist, wordfreq))))
```

```
String
it was the best of times it was the worst of times it was the age of wisdom it was the age of foolishness

List
['it', 'was', 'the', 'best', 'of', 'times', 'it', 'was', 'the', 'worst', 'of', 'times', 'it', 'was', 'the', 'age', 'of', 'wisdom', 'it', 'was', 'the', 'age', 'of', 'foolishness']

Frequencies
[4, 4, 4, 1, 4, 2, 4, 4, 4, 1, 4, 2, 4, 4, 4, 2, 4, 1, 4, 4, 4, 2, 4, 1]

Pairs
[('it', 4), ('was', 4), ('the', 4), ('best', 1), ('of', 4), ('times', 2), ('it', 4), ('was', 4), ('the', 4), ('worst', 1), ('of', 4), ('times', 2), ('it', 4), ('was', 4), ('the', 4), ('age', 2), ('of', 4), ('wisdom', 1), ('it', 4), ('was', 4), ('the', 4), ('age', 2), ('of', 4), ('foolishness', 1)]

```

### Python Dictionaries
As we start getting a feel of counting word frequencies with Python, we divert our attention to a very important data structure that can make counting word frequencies easy - a dictionary.

```python
d = {'world': 1, 'hello': 0}
print(d['hello'])

print(d['world'])

print(d.keys())
```

```
0
1
dict_keys(['world', 'hello'])
```

### Word-Frequency Pairs
The existing `obo.py` code is
```python
# obo.py
def stripTags(pageContents):
    pageContents = str(pageContents)
    startLoc = pageContents.find("<p>")
    endLoc = pageContents.rfind("<br/>")

    pageContents = pageContents[startLoc:endLoc]

    inside = 0
    text = ''

    for char in pageContents:
        if char == '<':
            inside = 1
        elif (inside == 1 and char == '>'):
            inside = 0
        elif inside == 1:
            continue
        else:
            text += char

    return text

# Given a text string, remove all non-alphanumeric
# characters (using Unicode definition of alphanumeric).

def stripNonAlphaNum(text):
    import re
    return re.compile(r'\W+', re.UNICODE).split(text)
```

We add the function `wordListToFreqDict` to this module.
```python
# Given a list of words, return a dictionary of word-frequency pairs
def wordListToFreqDict(wordlist):
    wordfreq = [wordlist.count(p) for p in wordlist]
    return dict(list(zip(wordlist,wordfreq)))
```

Furthermore, the function `sortFreqDict` is also added:
```python
# Sort a dictionary of word-frequency pairs in order of descending frequency
def sortFreqDict(freqdict):
    aux = [(freqdict[key], key) for key in freqdict]
    aux.sort()
    aux.reverse()
    return aux
```