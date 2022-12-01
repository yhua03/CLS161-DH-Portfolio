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

