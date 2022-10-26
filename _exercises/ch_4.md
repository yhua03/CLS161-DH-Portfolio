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

### 4-3. Counting to Twenty
Use a `for` loop to print the numbers from 1 to 20, inclusive.

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
Use the third argument of the `range()` function to make a list of the odd numbers from 1 to 20. Use a `for` loop to print each number.

```python
odd = range(1, 21, 2)
for numb in odd:
        print(numb)
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
- Print the message "The first three items in the list are:". Then use a slice to print the first three items from that program’s list.
- Print the message "Three items from the middle of the list are:". Use a slice to print three items from the middle of the list.
- Print the message "The last three items in the list are:". Use a slice to print the last three items in the list.

```python
animals = ["cat", "dog", "lion", "monkey", "tiger", "moose"]
///first task///
print(f"The first three items in the list are: ", end='')
for animal in animals[:3]:
    print(animal, end=' ')

///second task///
print(f"Two items from the middle of the list are: ", end='')
for animal in animals[2:4]:
    print(animal, end=' ')
    
///thrid task///
print(f"The last three items in the list are: ", end='')
for animal in animals[3:6]:
    print(animal, end=' ')
```
The first three items in the list are: cat dog lion 
Two items from the middle of the list are: lion monkey 
The last three items in the list are: monkey tiger moose 

