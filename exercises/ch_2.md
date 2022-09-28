---
layout: page
title: HW2 Python
description: HW2 Python
---

## _Python Crash Course_ Chapter 2

### 2-1. Simple Message
Assign a message to a variable, and then print that message.


```python
message = "hello world"
print(message)
```

    Hello World


### 2-2. Simple Messages
Assign a message to a variable, and print that message. Then change the value of the variable to a new message, and print the new message.


```python
message = "Hello world"
print(message)
message = "Bye world"
print(message)
```

    Hello world
    Bye world

### 2-3. Personal Message
Use a variable to represent a person’s name, and print a message to that person. Your message should be simple, such as, “Hello Eric, would you like to learn some Python today?”


```python
person = "Frank"
message = f"Hello {person}, would you like to learn some Python today?"
print(message)
```

    Hello Frank, would you like to learn some Python today?


### 2-4. Name Cases
Use a variable to represent a person’s name, and then print that person’s name in lowercase, uppercase, and title case.


```python
person = "frank hua"
print(person.lower())
print(person.upper())
print(person.title())
```

    frank hua
    FRANK HUA
    Frank Hua


### 2-5. Famous Quote
Find a quote from a famous person you admire. Print the quote and the name of its author.


```python
message = "Steve Jobs said : Stay hungry, stay foolish"
print(message)
```

    Steve Jobs said : Stay hungry, stay foolish


### 2-6. Famous Quote 2
Repeat Exercise 2-5, but this time, represent the famous person’s name using a variable called `famous_person`. Then compose your message and represent it with a new variable called `message`. Print your message.


```python
famous_person = Steve Jobs
message = f"{famous_person} said : Stay hungry, stay foolish"
print(message)
```

    Steve Jobs said : Stay hungry, stay foolish


### 2-7. Stripping Names
Use a variable to represent a person’s name, and include some whitespace characters at the beginning and end of the name. Make sure you use each character combination, "\t" and "\n", at least once.


```python
person = "\nFrank Hua\t"
print(person)
print(person.lstrip())
print(person.rstrip())
print(person.strip())
```

    
    Frank Hua	
    Frank Hua  
    Frank Hua
    Frank Hua


### 2-10. Adding Comments
Choose two of the programs you’ve written, and add at least one comment to each.


```python
# This program prints a message "hello world"
message = "hello world"
print(message)
```

    Hello World


```python
# This program prints a famous quote from Steve Jobs
message = "Steve Jobs said : Stay hungry, stay foolish"
print(message)
```

    Steve Jobs said : Stay hungry, stay foolish
