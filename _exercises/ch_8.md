---
layout: page
title: HW 8 Python
description: HW 8 Python
---

## _Python Crash Course_ Chapter 8

### 8-1. Message

Write a function called `display_message()` that prints one sentence telling everyone what you are learning about in this chapter. Call the function, and make sure the message displays correctly.

```python
def display_message():
    print("Yay functions are so cool")
display_message()
```

Yay functions are so cool

### 8-2. Favorite Book

Write a function called `favorite_book()` that accepts one parameter, `title`. The function should print a message, such as "One of my favorite books is Alice in Wonderland". Call the function, making sure to include a book title as an argument in the function call.

```python
def favorite_book(title):
    print(f"One of my favorite books is {title}.")
favorite_book('Alice in Wonderland')
```

One of my favorite books is Alice in Wonderland.


### 8-3. T-Shirt

Write a function called `make_shirt()` that accepts a size and the text of a message that should be printed on the shirt. The function should print a sentence summarizing the size of the shirt and the message printed on it.

Call the function once using positional arguments to make a shirt. Call the function a second time using keyword arguments.


```python
def make_shirt(size, message):
    print(f'The size of the shirt is {size} and and printed message on the shirt is "{message}"')
make_shirt('L', 'Team Large')
make_shirt(message='Team Medium', size='M')
```

The size of the shirt is L and and printed message on the shirt is "Team Large"
The size of the shirt is M and and printed message on the shirt is "Team Medium"

### 8-5. Cities

Write a function called `describe_city()` that accepts the name of a city and its country. The function should print a simple sentence, such as "Reykjavik is in Iceland". Give the parameter for the country a default value. Call your function for three different cities, at least one of which is not in the default country.

```python
def describe_city(city, country):
    print(f"{city} is in {country}")
describe_city('Boston', 'U.S')
describe_city('Shanghai', 'China')
```

Boston is in U.S
Shanghai is in China


### 8-6. City Names

Write a function called `city_country()` that takes in the name of a city and its country. The function should return a string formatted like this: "Santiago, Chile"

Call your function with at least three city-country pairs, and print the value that’s returned.


```python
def city_country(city, country):
    return f"{city}, {country}"
print(city_country('Shanghai', 'China'))
print(city_country('Boston', 'U.S'))
```

Shanghai, China
Boston, U.S
