---
layout: page
title: Exercises Ch. 4
description: Select exercises from Python Crash Course
---

## Python Crash Course Chapter 4

### 4-1. Pizzas
Think of at least three kinds of your favorite pizza. Store these pizza names in a list, and then use a for loop to print the name of each pizza.

- Modify your for loop to print a sentence using the name of the pizza instead of printing just the name of the pizza. For each pizza you should have one line of output containing a simple statement like I like pepperoni pizza.
- Add a line at the end of your program, outside the for loop, that states how much you like pizza. The output should consist of three or more lines about the kinds of pizza you like and then an additional sentence, such as I really love pizza!


```python
pizzas = ["pepperoni", "cheese", "mushroom"]
for pizza in pizzas:
    print(pizza)

for pizza in pizzas:
    print(f"{pizza.title()} pizza is the greatest pizza ever.")

for pizza in pizzas:
    print(f"{pizza.title()} pizza is my favorite pizza!")
print("If I was asked to choose between my family or pizza, I'd choose pizza.")
```

    pepperoni
    cheese
    mushroom
    Pepperoni pizza is the greatest pizza ever.
    Cheese pizza is the greatest pizza ever.
    Mushroom pizza is the greatest pizza ever.
    Pepperoni pizza is my favorite pizza!
    Cheese pizza is my favorite pizza!
    Mushroom pizza is my favorite pizza!
    If I was asked to choose between my family or pizza, I'd choose pizza.


### 4-2. Animals
Think of at least three different animals that have a common characteristic. Store the names of these animals in a list, and then use a for loop to print out the name of each animal.

- Modify your program to print a statement about each animal, such as A dog would make a great pet.
- Add a line at the end of your program stating what these animals have in common. You could print a sentence such as Any of these animals would make a great pet!


```python
animals = ["cat", "dog", "hamster"]

for animal in animals:
    print(animal)

for animal in animals:
    print(f"A {animal} would make a great pet!")

print("These are all animals that could be domesticated and trained.")
```

    cat
    dog
    hamster
    A cat would make a great pet!
    A dog would make a great pet!
    A hamster would make a great pet!
    These are all animals that could be domesticated and trained.


### 4-3. Counting to Twenty
Use a for loop to print the numbers from 1 to 20, inclusive.


```python
for num in range(1,21):
    print(num)
```

    1
    2
    3
    4
    5
    6
    7
    8
    9
    10
    11
    12
    13
    14
    15
    16
    17
    18
    19
    20


### 4-6. Odd Numbers
Use the third argument of the range() function to make a list of the odd numbers from 1 to 20. Use a for loop to print each number.


```python
odd_numbers = range(1, 21, 2)
for num in odd_numbers:
    print(num)
```

    1
    3
    5
    7
    9
    11
    13
    15
    17
    19


### 4-10. Slices
Using one of the programs you wrote in this chapter, add several lines to the end of the program that do the following:

- Print the message The first three items in the list are:. Then use a slice to print the first three items from that program’s list.
- Print the message Three items from the middle of the list are:. Use a slice to print three items from the middle of the list.
- Print the message The last three items in the list are:. Use a slice to print the last three items in the list.


```python
# I'll create a new list of types of pizzas for this exercise
pizzas = ["pepperoni", "cheese", "mushroom", "chicago", "greek", "sausage", "pineapple", "hawaiian", "sicilian"]

print(f"The first three items in the list are: ", end='')
for pizza in pizzas[:3]:
    print(pizza, end=' ')
    
print("\nThree items from the middle of the list are: ", end='')
for pizza in pizzas[3:6]:
    print(pizza, end=' ')
    
print("\nThe last three items in the list are: ", end='')
for pizza in pizzas[6:]:
    print(pizza, end=' ')
```

    The first three items in the list are: pepperoni cheese mushroom 
    Three items from the middle of the list are: chicago greek sausage 
    The last three items in the list are: pineapple hawaiian sicilian 

### 4-11. My Pizzas, Your Pizzas
Start with your program from Exercise 4-1. Make a copy of the list of pizzas, and call it `friend_pizzas`. Then, do the following:

- Add a new pizza to the original list.
- Add a different pizza to the list friend_pizzas.
- Prove that you have two separate lists. Print the message My favorite pizzas are:, and then use a for loop to print the first list. Print the message My friend’s favorite pizzas are:, and then use a for loop to print the second list. Make sure each new pizza is stored in the appropriate list.


```python
pizzas = ["pepperoni", "cheese", "mushroom"]
friend_pizzas = pizzas[:]

pizzas.append("sicilian")

friend_pizzas.append("pineapple")

print("My favorite pizzas are:")
for pizza in pizzas:
    print(pizza)
    
print("My friend's favorite pizzas are:")
for pizza in friend_pizzas:
    print(pizza)
```

    My favorite pizzas are:
    pepperoni
    cheese
    mushroom
    sicilian
    My friend's favorite pizzas are:
    pepperoni
    cheese
    mushroom
    pineapple

