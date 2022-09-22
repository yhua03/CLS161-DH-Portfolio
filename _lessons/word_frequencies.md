---
layout: page
title: Counting Word Frequencies with Python
description: This lesson uses Python to count word frequencies, which can be used in several ways to analyze texts.
---

## Source
[Turkel, W. J., & Crymble, A. (2012). Counting Word Frequencies with Python. _The Programming Historian_, 1. https://doi.org/10.46430/phen0003](https://programminghistorian.org/en/lessons/counting-frequencies)

## Reflection
Word frequency counting in text is a modern (intermediate) method of text analysis. I say it is an intermediate method because word frequency on its own does not allow us to completely summarize the text we're analyzing, but it ends up giving us a lot of information that we can then use in other advanced stages of analyzing text.

With that said, it is important to understand that this technique does not only give us information of what the most commonly used word is in that particular text, but also helps us 
infer the abstract of the text. In other words, gaining access to most commonly used words in a text is not just the superficial statistic where one has the access to 
most frequently occuring words in the text, it has a deeper meaning to it in the sense that the most frequently occurring words alone can help us decipher what message the text is trying to convey and in what subject.  In this example from the Programming Historian, Python dictionaries are used to accomplish this with the goal of analyzing text contents in meaningful ways.

I was freely able to follow all methods and concepts discussed in this lesson. The code was 
simple enough to follow and the only complicated part was figuring out what was going on with 
zip and maps. I quite liked how the final implementation took URLs as input which made the program more versatile. This is immensely helpful in the field of Digital Humanities, for we can analyze online texts without having to have a local copy of the source.

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

Finally, we can use these functions to write a program that takes a URL and returns the word-frequency pairs for that webpage, sorted in descending order of the word's frequency.

```python
# html-to-freq.py

import urllib.request, urllib.error, urllib.parse, obo

url = 'http://www.oldbaileyonline.org/browse.jsp?id=t17800628-33&div=t17800628-33'

response = urllib.request.urlopen(url)
html = response.read().decode('UTF-8')
text = obo.stripTags(html).lower()
wordlist = obo.stripNonAlphaNum(text)
dictionary = obo.wordListToFreqDict(wordlist)
sorteddict = obo.sortFreqDict(dictionary)

for s in sorteddict: print(str(s))
```

```
(192, 'the')
(105, 'i')
(74, 'to')
(71, 'was')
(67, 'of')
(62, 'in')
(53, 'a')
(52, 'and')
(50, 'you')
(50, 'he')
(40, 'that')
(38, 'his')
(36, 'it')
(34, 'did')
(27, 'him')
(26, 'on')
(26, 'at')
(25, 'house')
(23, 'had')
(21, 'there')
(21, 'my')
(20, 'yes')
(20, 's')
(20, 'prisoner')
(20, 'any')
(19, 'not')
(19, 'mr')
(18, 'were')
(17, 'when')
(17, 'man')
(15, 'what')
(15, 'no')
(15, 'akerman')
(14, 'with')
(14, 'mob')
(13, 'black')
(12, 'this')
(12, 'them')
(12, 'night')
(12, 'is')
(12, 'down')
(12, 'are')
(11, 'up')
(11, 'they')
(11, 'some')
(11, 'saw')
(11, 'other')
(11, 'do')
(11, 'but')
(10, 'which')
(10, 'see')
(9, 'went')
(9, 'then')
(9, 'sworn')
(9, 'room')
(9, 'pair')
(9, 'out')
(9, 'me')
(9, 'know')
(9, 'fire')
(9, 'face')
(9, 'by')
(9, 'be')
(9, 'am')
(8, 'who')
(8, 'time')
(8, 'thing')
(8, 'one')
(8, 'for')
...
...
```
_Note:_ output is suppressed because it's too long.

### Removing Stop Words
Analyzing the previous output, we can see that the most frequently occurring words are "the", "i", etc. This is not helpful to us and since we are interested in finding the words
that will help us differentiate this text from others, we will filter out the common 
words. These words are called stop words.

The list of stopwords used below is obtained from [this source](http://ir.dcs.gla.ac.uk/resources/linguistic_utils/stop_words).

```python
stopwords = ['a', 'about', 'above', 'across', 'after', 'afterwards']
stopwords += ['again', 'against', 'all', 'almost', 'alone', 'along']
stopwords += ['already', 'also', 'although', 'always', 'am', 'among']
stopwords += ['amongst', 'amoungst', 'amount', 'an', 'and', 'another']
stopwords += ['any', 'anyhow', 'anyone', 'anything', 'anyway', 'anywhere']
stopwords += ['are', 'around', 'as', 'at', 'back', 'be', 'became']
stopwords += ['because', 'become', 'becomes', 'becoming', 'been']
stopwords += ['before', 'beforehand', 'behind', 'being', 'below']
stopwords += ['beside', 'besides', 'between', 'beyond', 'bill', 'both']
stopwords += ['bottom', 'but', 'by', 'call', 'can', 'cannot', 'cant']
stopwords += ['co', 'computer', 'con', 'could', 'couldnt', 'cry', 'de']
stopwords += ['describe', 'detail', 'did', 'do', 'done', 'down', 'due']
stopwords += ['during', 'each', 'eg', 'eight', 'either', 'eleven', 'else']
stopwords += ['elsewhere', 'empty', 'enough', 'etc', 'even', 'ever']
stopwords += ['every', 'everyone', 'everything', 'everywhere', 'except']
stopwords += ['few', 'fifteen', 'fifty', 'fill', 'find', 'fire', 'first']
stopwords += ['five', 'for', 'former', 'formerly', 'forty', 'found']
stopwords += ['four', 'from', 'front', 'full', 'further', 'get', 'give']
stopwords += ['go', 'had', 'has', 'hasnt', 'have', 'he', 'hence', 'her']
stopwords += ['here', 'hereafter', 'hereby', 'herein', 'hereupon', 'hers']
stopwords += ['herself', 'him', 'himself', 'his', 'how', 'however']
stopwords += ['hundred', 'i', 'ie', 'if', 'in', 'inc', 'indeed']
stopwords += ['interest', 'into', 'is', 'it', 'its', 'itself', 'keep']
stopwords += ['last', 'latter', 'latterly', 'least', 'less', 'ltd', 'made']
stopwords += ['many', 'may', 'me', 'meanwhile', 'might', 'mill', 'mine']
stopwords += ['more', 'moreover', 'most', 'mostly', 'move', 'much']
stopwords += ['must', 'my', 'myself', 'name', 'namely', 'neither', 'never']
stopwords += ['nevertheless', 'next', 'nine', 'no', 'nobody', 'none']
stopwords += ['noone', 'nor', 'not', 'nothing', 'now', 'nowhere', 'of']
stopwords += ['off', 'often', 'on','once', 'one', 'only', 'onto', 'or']
stopwords += ['other', 'others', 'otherwise', 'our', 'ours', 'ourselves']
stopwords += ['out', 'over', 'own', 'part', 'per', 'perhaps', 'please']
stopwords += ['put', 'rather', 're', 's', 'same', 'see', 'seem', 'seemed']
stopwords += ['seeming', 'seems', 'serious', 'several', 'she', 'should']
stopwords += ['show', 'side', 'since', 'sincere', 'six', 'sixty', 'so']
stopwords += ['some', 'somehow', 'someone', 'something', 'sometime']
stopwords += ['sometimes', 'somewhere', 'still', 'such', 'system', 'take']
stopwords += ['ten', 'than', 'that', 'the', 'their', 'them', 'themselves']
stopwords += ['then', 'thence', 'there', 'thereafter', 'thereby']
stopwords += ['therefore', 'therein', 'thereupon', 'these', 'they']
stopwords += ['thick', 'thin', 'third', 'this', 'those', 'though', 'three']
stopwords += ['three', 'through', 'throughout', 'thru', 'thus', 'to']
stopwords += ['together', 'too', 'top', 'toward', 'towards', 'twelve']
stopwords += ['twenty', 'two', 'un', 'under', 'until', 'up', 'upon']
stopwords += ['us', 'very', 'via', 'was', 'we', 'well', 'were', 'what']
stopwords += ['whatever', 'when', 'whence', 'whenever', 'where']
stopwords += ['whereafter', 'whereas', 'whereby', 'wherein', 'whereupon']
stopwords += ['wherever', 'whether', 'which', 'while', 'whither', 'who']
stopwords += ['whoever', 'whole', 'whom', 'whose', 'why', 'will', 'with']
stopwords += ['within', 'without', 'would', 'yet', 'you', 'your']
stopwords += ['yours', 'yourself', 'yourselves']
```
With this list and the following `removeStopwords` function added to `obo.py`, our output 
is more meaningful than before.
```python
# Given a list of words, remove any that are in a list of stop words
def removeStopwords(wordlist, stopwords):
    return [w for w in wordlist if w not in stopwords]
```

### Putting it All Together
We now will use the methods we defined to create a word frequency counter that ignores the stop words.
```python
# html-to-freq-2.py

import urllib.request, urllib.error, urllib.parse
import obo

url = 'http://www.oldbaileyonline.org/browse.jsp?id=t17800628-33&div=t17800628-33'

response = urllib.request.urlopen(url)
html = response.read().decode('UTF-8')
text = obo.stripTags(html).lower()
fullwordlist = obo.stripNonAlphaNum(text)
wordlist = obo.removeStopwords(fullwordlist, obo.stopwords)
dictionary = obo.wordListToFreqDict(wordlist)
sorteddict = obo.sortFreqDict(dictionary)

for s in sorteddict: print(str(s))
```

```
(25, 'house')
(20, 'yes')
(20, 'prisoner')
(19, 'mr')
(17, 'man')
(15, 'akerman')
(14, 'mob')
(13, 'black')
(12, 'night')
(11, 'saw')
(9, 'went')
(9, 'sworn')
(9, 'room')
(9, 'pair')
(9, 'know')
(9, 'face')
(8, 'time')
(8, 'thing')
(8, 'believe')
(7, 'window')
(7, 'took')
(7, 'swear')
...
```
_Note:_ output is suppressed because it's too long.

And just like that, we have built a fully functional word frequency counter!