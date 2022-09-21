---
layout: page
title: Exercises Ch. 3
description: Select exercises from Python Crash Course
---

## _Python Crash Course_ Chapter 2

### 2-1. Simple Message
Assign a message to a variable, and then print that message.


```python
my_message = "This is my message"
print(my_message)
```

    This is my message


### 2-2. Simple Messages
Assign a message to a variable, and print that message. Then change the value of the variable to a new message, and print the new message.


```python
my_message = "This is my message"
print(my_message)
my_message = "This is my new message"
print(my_message)
```

    This is my message
    This is my new message


### 2-3. Personal Message
Use a variable to represent a person’s name, and print a message to that person. Your message should be simple, such as, “Hello Eric, would you like to learn some Python today?”


```python
person = "Thomas"
message = f"Hello {person}, would you like to learn some Python today?"
print(message)
```

    Hello Thomas, would you like to learn some Python today?


### 2-4. Name Cases
Use a variable to represent a person’s name, and then print that person’s name in lowercase, uppercase, and title case.


```python
person = "ankur Dahal"
print(person.lower())
print(person.upper())
print(person.title())
```

    ankur dahal
    ANKUR DAHAL
    Ankur Dahal


### 2-5. Famous Quote
Find a quote from a famous person you admire. Print the quote and the name of its author.


```python
print('Albert Einstein once said, “A person who never made a mistake never tried anything new.”')
```

    Albert Einstein once said, “A person who never made a mistake never tried anything new.”


### 2-6. Famous Quote 2
Repeat Exercise 2-5, but this time, represent the famous person’s name using a variable called `famous_person`. Then compose your message and represent it with a new variable called `message`. Print your message.


```python
famous_person = 'Albert Einstein'
message = f'{famous_person} once said, “A person who never made a mistake never tried anything new.”'
print(message)
```

    Albert Einstein once said, “A person who never made a mistake never tried anything new.”


### 2-7. Stripping Names
Use a variable to represent a person’s name, and include some whitespace characters at the beginning and end of the name. Make sure you use each character combination, "\t" and "\n", at least once.


```python
person_name = "\nAnkur Dahal\t"
print(person_name)
print(person_name.lstrip())
print(person_name.rstrip())
print(person_name.strip())
```

    
    Ankur Dahal	
    Ankur Dahal	
    
    Ankur Dahal
    Ankur Dahal


### 2-10. Adding Comments
Choose two of the programs you’ve written, and add at least one comment to each.


```python
# This program prints a quote from Albert Einstein
famous_person = 'Albert Einstein'
message = f'{famous_person} once said, “A person who never made a mistake never tried anything new.”' # We use f string here to easily substitute the variable name for its value
print(message)
```

    Albert Einstein once said, “A person who never made a mistake never tried anything new.”



```python
# This program prints the value of a string stored in `person` in lowercase, uppercase, and title case
person = "ankur Dahal"
print(person.lower())
print(person.upper())
print(person.title())
```

    ankur dahal
    ANKUR DAHAL
    Ankur Dahal

