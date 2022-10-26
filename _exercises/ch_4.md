---
layout: page
title: HW4 Python
description: HW4 Python
---

## _Python Crash Course_ Chapter 4
### 4-1. Pizzas
Think of at least three kinds of your favorite pizza. Store these pizza names in a list, and then use a `for` loop to print the name of each pizza.

- Modify your `for` loop to print a sentence using the name of the pizza instead of printing just the name of the pizza. For each pizza you should have one line of output containing a simple statement like "I like pepperoni pizza".
- Add a line at the end of your program, outside the `for` loop, that states how much you like pizza. The output should consist of three or more lines about the kinds of pizza you like and then an additional sentence, such as "I really love pizza!"

```python
pizza_types = ["cheese", "hawaian", "meat"]
for pizza in pizza_types:
    print(pizza)
for pizza in pizza_types:
    print(f"I really like{pizza.title()}pizza.")
for pizza in pizza_types:
    print(f"{pizza.title()} pizza is the best.")
print("Nothing can compare to pizzas")
```
cheese
hawaian
meat
I really likeCheesepizza.
I really likeHawaianpizza.
I really likeMeatpizza.
Cheese pizza is the best.
Hawaian pizza is the best.
Meat pizza is the best.
Nothing can compare to pizzas

### 4-2. Animals
Think of at least three different animals that have a common characteristic. Store the names of these animals in a list, and then use a `for` loop to print out the name of each animal.

- Modify your program to print a statement about each animal, such as "A dog would make a great pet".
- Add a line at the end of your program stating what these animals have in common. You could print a sentence such as "Any of these animals would make a great pet!"
- 
```python
animals = ["cat", "dog", "lion"]
for animal in animals:
    print(animal)
for animal in animals:
    print(f"I have a {animal} at home as a pet ")
print("All are very kind and tamable creatures:)")
```
cat
dog
lion
I have a cat at home as a pet 
I have a dog at home as a pet 
I have a lion at home as a pet 
All are very kind and tamable creatures:)
