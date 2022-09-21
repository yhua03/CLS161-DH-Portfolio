---
layout: page
title: Exercises Ch. 6
description: Select exercises from Python Crash Course
---

## _Python Crash Course_ Chapter 6

### 6-1. Person

Use a dictionary to store information about a person you know. Store their first name, last name, age, and the city in which they live. You should have keys such as `first_name`, `last_name`, `age`, and `city`. Print each piece of information stored in your dictionary.


```python
person_info = {'first_name' : 'Ankur', 'last_name' : 'Dahal' , 'age' : 21, 'city' : 'Boston'}
for key, value in person_info.items():
    print(f"{key}: {value}")
```

    first_name: Ankur
    last_name: Dahal
    age: 21
    city: Boston


### 6-2. Favorite Numbers

Use a dictionary to store people’s favorite numbers. Think of five names, and use them as keys in your dictionary. Think of a favorite number for each person, and store each as a value in your dictionary. Print each person’s name and their favorite number. For even more fun, poll a few friends and get some actual data for your program.


```python
favorite_numbers = {'Ankur' : 7, 'Ellis' : 0, 'Yuma' : 213, 'Thomas' : 9, 'Etha' : 92}
for name, number in favorite_numbers.items():
    print(f"{name.title()}'s favorite number is {number}!")
```

    Ankur's favorite number is 7!
    Ellis's favorite number is 0!
    Yuma's favorite number is 213!
    Thomas's favorite number is 9!
    Etha's favorite number is 92!


### 6-3. Glossary

A Python dictionary can be used to model an actual dictionary. However, to avoid confusion, let’s call it a glossary.

 - Think of five programming words you’ve learned about in the previous chapters. Use these words as the keys in your glossary, and store their meanings as values.

 - Print each word and its meaning as neatly formatted output. You might print the word followed by a colon and then its meaning, or print the word on one line and then print its meaning indented on a second line. Use the newline character (\n) to insert a blank line between each word-meaning pair in your output.


```python
glossary = {'variable' : 'A location in memory where mutable values are stored', 
            'constant' : 'A location in memory where values are stored and they can not be changed during execution time',
            'conditional statement' : 'A statement that executes a branch of code depending on the conditional expression it evaluates',
            'literal' : 'A constant value',
            'environment' : 'A set of name-value bindings where an expression is evaluated'
            }

print(f"variable: {glossary['variable']}")
print(f"\nconstant: {glossary['constant']}")
print(f"\nconditional statement: {glossary['conditional statement']}")
print(f"\nliteral: {glossary['literal']}")
print(f"\nenvironment: {glossary['environment']}")


# for word, meaning in glossary.items():
#     print(f"{word}: {meaning}\n")
```

    variable: A location in memory where mutable values are stored
    
    constant: A location in memory where values are stored and they can not be changed during execution time
    
    conditional statement: A statement that executes a branch of code depending on the conditional expression it evaluates
    
    literal: A constant value
    
    environment: A set of name-value bindings where an expression is evaluated


### 6-4. Glossary 2

Now that you know how to loop through a dictionary, clean up the code from Exercise 6-3 by replacing your series of print statements with a loop that runs through the dictionary’s keys and values. When you’re sure that your loop works, add five more Python terms to your glossary. When you run your program again, these new words and meanings should automatically be included in the output.


```python
glossary = {'variable' : 'A location in memory where mutable values are stored', 
            'constant' : 'A location in memory where values are stored and they can not be changed during execution time',
            'conditional statement' : 'A statement that executes a branch of code depending on the conditional expression it evaluates',
            'literal' : 'A constant value',
            'environment' : 'A set of name-value bindings where an expression is evaluated',
            'loop' : 'A programming construct where a body of code is repeated for a certain number of times, or until a given condition is satisfied',
            'interpreter' : 'A program that executes code and prints its output, line by line',
            'compiler' : 'A program that compiles source code to an executable',
            'lambda' : 'An anonymous function',
            'list' : 'A data structure used for storing values'
            }

for word, meaning in glossary.items():
    print(f"{word}: {meaning}\n")
```

    variable: A location in memory where mutable values are stored
    
    constant: A location in memory where values are stored and they can not be changed during execution time
    
    conditional statement: A statement that executes a branch of code depending on the conditional expression it evaluates
    
    literal: A constant value
    
    environment: A set of name-value bindings where an expression is evaluated
    
    loop: A programming construct where a body of code is repeated for a certain number of times, or until a given condition is satisfied
    
    interpreter: A program that executes code and prints its output, line by line
    
    compiler: A program that compiles source code to an executable
    
    lambda: An anonymous function
    
    list: A data structure used for storing values
    


### 6-5. Rivers

Make a dictionary containing three major rivers and the country each river runs through. One key-value pair might be 'nile': 'egypt'.

 - Use a loop to print a sentence about each river, such as "The Nile runs through Egypt."

 - Use a loop to print the name of each river included in the dictionary.

 - Use a loop to print the name of each country included in the dictionary.


```python
rivers = {'nile' : 'egypt', 'bagmati' : 'nepal', 'ganges' : 'india'}
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
    The Bagmati runs through Nepal
    The Ganges runs through India
    Nile
    Bagmati
    Ganges
    Egypt
    Nepal
    India


### 6-7. People

Start with the program you wrote for Exercise 6-1. Make two new dictionaries representing different people, and store all three dictionaries in a list called `people`. Loop through your list of people. As you loop through the list, print everything you know about each person.


```python
person_info = {'first_name' : 'Ankur', 'last_name' : 'Dahal' , 'age' : 21, 'city' : 'Boston'}
person2_info = {'first_name' : 'Ellis', 'last_name' : 'Brown' , 'age' : 21, 'city' : 'Somerville'}
person3_info = {'first_name' : 'Etha', 'last_name' : 'Hua' , 'age' : 22, 'city' : 'Medford'}

people = [person_info, person2_info, person3_info]

for person in people:
    for key, value in person.items():
        print(f"{key}: {value}")
    print()
```

    first_name: Ankur
    last_name: Dahal
    age: 21
    city: Boston
    
    first_name: Ellis
    last_name: Brown
    age: 21
    city: Somerville
    
    first_name: Etha
    last_name: Hua
    age: 22
    city: Medford
    


### 6-8. Pets

Make several dictionaries, where the name of each dictionary is the name of a pet. In each dictionary, include the kind of animal and the owner’s name. Store these dictionaries in a list called `pets`. Next, loop through your list and as you do print everything you know about each pet.


```python
Bruno = {'name' : 'Bruno', 'age' : 3, 'kind' : 'dog', 'owner' : 'Ankur'}
Kitty = {'name' : 'Kitty', 'age' : 1, 'kind' : 'cat', 'owner' : 'Ellis'}

pets = [Bruno, Kitty]

for pet in pets:
    for key, value in pet.items():
        print(f"{key}: {value}")
    print()
```

    name: Bruno
    age: 3
    kind: dog
    owner: Ankur
    
    name: Kitty
    age: 1
    kind: cat
    owner: Ellis
    


### 6-9. Favorite Places

Make a dictionary called `favorite_places`. Think of three names to use as keys in the dictionary, and store one to three favorite places for each person. To make this exercise a bit more interesting, ask some friends to name a few of their favorite places. Loop through the dictionary, and print each person’s name and their favorite places.


```python
favorite_places = {'Ankur' : ['Boston Commons', 'JCC', 'Patan'],
                   'Ellis' : ['Adam St'],
                   'Thomas' : ['London', 'Pittsburg']}

for person, places in favorite_places.items():
    print(f"{person.title()}'s favorite places are:")
    for place in places:
        print(place)
    print()
```

    Ankur's favorite places are:
    Boston Commons
    JCC
    Patan
    
    Ellis's favorite places are:
    Adam St
    
    Thomas's favorite places are:
    London
    Pittsburg
    


### 6-11. Cities

Make a dictionary called `cities`. Use the names of three cities as keys in your dictionary. Create a dictionary of information about each city and include the country that the city is in, its approximate population, and one fact about that city. The keys for each city’s dictionary should be something like `country`, `population`, and `fact`. Print the name of each city and all of the information you have stored about it.


```python
cities = {'Kathmandu' : {'country' : 'Nepal', 'population' : 850_000, 'fact' : 'Kathmandu is known as the "city of temples"!'},
          'Boston' : {'country' : 'United States', 'population' : 675_800, 'fact' : 'Boston is named after a town in England.'},
          'London' : {'country' : 'England', 'population' : 9_000_000, 'fact' : 'Over 300 languages are spoken in London.'}}

for city, info in cities.items():
    print("City: " + city)
    for key, value in info.items():
        print(f"{key.title()}: {value}")
    print()
```

    City: Kathmandu
    Country: Nepal
    Population: 850000
    Fact: Kathmandu is known as the "city of temples"!
    
    City: Boston
    Country: United States
    Population: 675800
    Fact: Boston is named after a town in England.
    
    City: London
    Country: England
    Population: 9000000
    Fact: Over 300 languages are spoken in London.
    

