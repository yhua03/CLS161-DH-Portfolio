---
layout: page
title: Exercises Ch. 8
description: Select exercises from Python Crash Course
---

## _Python Crash Course_ Chapter 8

### 8-1. Message

Write a function called `display_message()` that prints one sentence telling everyone what you are learning about in this chapter. Call the function, and make sure the message displays correctly.


```python
def display_message():
    print("I am learning about functions in this chapter!")

display_message()
```

    I am learning about functions in this chapter!


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
def make_shirt(size, message_text):
    print(f'The size of the shirt is {size} and the message to be printed on it is "{message_text}"')

# calling make_shirt using positional arguments
make_shirt('M', 'We rock')

# calling make_shirt using keyword arguments
make_shirt(message_text='We rock!', size='L')
```

    The size of the shirt is M and the message to be printed on it is "We rock"
    The size of the shirt is L and the message to be printed on it is "We rock!"


### 8-5. Cities

Write a function called `describe_city()` that accepts the name of a city and its country. The function should print a simple sentence, such as "Reykjavik is in Iceland". Give the parameter for the country a default value. Call your function for three different cities, at least one of which is not in the default country.


```python
def describe_city(city, country='the United States'):
    print(f"{city} is in {country}")

describe_city('Boston')
describe_city('Kathmandu', 'Nepal')
describe_city('Doha', 'Qatar')
```

    Boston is in the United States
    Kathmandu is in Nepal
    Doha is in Qatar


### 8-6. City Names

Write a function called `city_country()` that takes in the name of a city and its country. The function should return a string formatted like this: "Santiago, Chile"

Call your function with at least three city-country pairs, and print the value that’s returned.


```python
def city_country(city, country):
    return f"{city}, {country}"

print(city_country('Santiago', 'Chile'))
print(city_country('Kathmandu', 'Nepal'))
print(city_country('Doha', 'Qatar'))
```

    Santiago, Chile
    Kathmandu, Nepal
    Doha, Qatar


### 8-7. Album

Write a function called `make_album()` that builds a dictionary describing a music album. The function should take in an artist name and an album title, and it should return a dictionary containing these two pieces of information. Use the function to make three dictionaries representing different albums. Print each return value to show that the dictionaries are storing the album information correctly.

Add an optional parameter to `make_album()` that allows you to store the number of tracks on an album. If the calling line includes a value for the number of tracks, add that value to the album’s dictionary. Make at least one new function call that includes the number of tracks on an album.


```python
def make_album(artist_name, album_title, num_tracks=-1):
    if num_tracks != -1:
        return {'artist_name' : artist_name, 'album_title' : album_title, 'num_tracks' : num_tracks}
    else:
        return {'artist_name' : artist_name, 'album_title' : album_title}

print(make_album('Ankur', 'Boooooooom'))
print(make_album('Ed Sheeran', 'Divide'))
print(make_album('Ellis', 'Dogs'))
print()
print(make_album('Etha', 'Nothing But Love', 4))
```

    {'artist_name': 'Ankur', 'album_title': 'Boooooooom'}
    {'artist_name': 'Ed Sheeran', 'album_title': 'Divide'}
    {'artist_name': 'Ellis', 'album_title': 'Dogs'}
    
    {'artist_name': 'Etha', 'album_title': 'Nothing But Love', 'num_tracks': 4}

