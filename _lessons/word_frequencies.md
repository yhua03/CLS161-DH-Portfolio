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