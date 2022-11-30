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
