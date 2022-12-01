---
layout: page
title: HW6 Python
description: HW6 Python
---

## _Python Crash Course_ Chapter 6

### 6-1. Person

Use a dictionary to store information about a person you know. Store their first name, last name, age, and the city in which they live. You should have keys such as `first_name`, `last_name`, `age`, and `city`. Print each piece of information stored in your dictionary

```python
person = {'first_name' : 'Frank', 'last_name' : 'Hua' , 'age' : 22, 'city' : 'Shanghai'}
for key, value in person.items():
    print(f"{key}: {value}")
```
first_name: Frank
last_name: Hua
age: 22
city: Shanghai

### 6-2. Favorite Numbers

Use a dictionary to store people’s favorite numbers. Think of five names, and use them as keys in your dictionary. Think of a favorite number for each person, and store each as a value in your dictionary. Print each person’s name and their favorite number. For even more fun, poll a few friends and get some actual data for your program.

```python
favorite_numbers = {'Frank' : 24, 'Cece' : 13, 'Justin' : 1108, 'Steph' : 1}
for name, number in favorite_numbers.items():
    print(f"{name.title()}'s favorite number is {number}!")
```
Frank's favorite number is 24!
Cece's favorite number is 13!
Justin's favorite number is 1108!
Steph's favorite number is 1!

### 6-3. Glossary

A Python dictionary can be used to model an actual dictionary. However, to avoid confusion, let’s call it a glossary.

 - Think of five programming words you’ve learned about in the previous chapters. Use these words as the keys in your glossary, and store their meanings as values.

 - Print each word and its meaning as neatly formatted output. You might print the word followed by a colon and then its meaning, or print the word on one line and then print its meaning indented on a second line. Use the newline character (\n) to insert a blank line between each word-meaning pair in your output.

```python
glossary = {'python' : 'a high-level, general-purpose programming language', 
            'string' : 'a sequence of characters, either as a literal constant or as some kind of variable',
            'Python variable' : 'a reference or pointer to an object',
            'boolean' : 'a result that can only have one of two possible values: true or false'
            }
print(f"python: {glossary['python']}")
print(f"\nstring: {glossary['string']}")
print(f"\nPython variable: {glossary['Python variable']}")
print(f"\nboolean: {glossary['boolean']}")
```

python: a high-level, general-purpose programming language

string: a sequence of characters, either as a literal constant or as some kind of variable

Python variable: a reference or pointer to an object

boolean: a result that can only have one of two possible values: true or false

### 6-4. Glossary 2

Now that you know how to loop through a dictionary, clean up the code from Exercise 6-3 by replacing your series of print statements with a loop that runs through the dictionary’s keys and values. When you’re sure that your loop works, add five more Python terms to your glossary. When you run your program again, these new words and meanings should automatically be included in the output.

```python
glossary = {'python' : 'a high-level, general-purpose programming language', 
            'string' : 'a sequence of characters, either as a literal constant or as some kind of variable',
            'Python variable' : 'a reference or pointer to an object',
            'boolean' : 'a result that can only have one of two possible values: true or false'
            }

for word, meaning in glossary.items():
    print(f"{word}: {meaning}\n")
```

python: a high-level, general-purpose programming language

string: a sequence of characters, either as a literal constant or as some kind of variable

Python variable: a reference or pointer to an object

boolean: a result that can only have one of two possible values: true or false

### 6-5. Rivers

Make a dictionary containing three major rivers and the country each river runs through. One key-value pair might be 'nile': 'egypt'.

 - Use a loop to print a sentence about each river, such as "The Nile runs through Egypt."

 - Use a loop to print the name of each river included in the dictionary.

 - Use a loop to print the name of each country included in the dictionary.

```python
rivers = {'nile' : 'egypt', 'yellow river' : 'china', 'amazon river' : 'brazil'}
for river, country in rivers.items():
    print(f"The {river.title()} runs through {country.title()}")
# name of rivers
for river in rivers.keys():
    print(river.title())
# countries in the dictionary
for country in rivers.values():
    print(country.title())
```

The Nile runs through Egypt
The Yellow River runs through China
The Amazon River runs through Brazil
Nile
Yellow River
Amazon River
Egypt
China
Brazil

### 6-7. People

Start with the program you wrote for Exercise 6-1. Make two new dictionaries representing different people, and store all three dictionaries in a list called `people`. Loop through your list of people. As you loop through the list, print everything you know about each person.

```python
person1 = {'first_name' : 'Frank', 'last_name' : 'Hua' , 'age' : 22, 'city' : 'Shanghai'}
person2 = {'first_name' : 'Rick', 'last_name' : 'Sanchez' , 'age' : 70, 'city' : 'Dimension C-137'}
person3 = {'first_name' : 'Cece', 'last_name' : 'Pan' , 'age' : 22, 'city' : 'Boston'}
people = [person1, person2, person3]
for person in people:
    for key, value in person.items():
        print(f"{key}: {value}")
    print()
```

first_name: Frank
last_name: Hua
age: 22
city: Shanghai

first_name: Rick
last_name: Sanchez
age: 70
city: Dimension C-137

first_name: Cece
last_name: Pan
age: 22
city: Boston

### 6-8. Pets

Make several dictionaries, where the name of each dictionary is the name of a pet. In each dictionary, include the kind of animal and the owner’s name. Store these dictionaries in a list called `pets`. Next, loop through your list and as you do print everything you know about each pet.

```python
Udon = {'name' : 'Udon', 'age' : 1, 'species' : 'cat'}
Tora = {'name' : 'Kitty', 'age' : 6, 'species' : 'cat'}
pets = [Udon, Tora]
for pet in pets:
    for key, value in pet.items():
        print(f"{key}: {value}")
    print()
```
name: Udon
age: 1
species: cat

name: Kitty
age: 6
species: cat
