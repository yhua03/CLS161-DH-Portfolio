---
layout: page
title: HW3 Python
description: HW3 Python
---

## _Python Crash Course_ Chapter 3
### 3-1. Names
Store the names of a few of your friends in a list called `names`. Print each person’s name by accessing each element in the list, one at a time.


```python
names = ["Frank", "Cece", "Justin", "Steph"]
print(names[0])
print(names[1])
print(names[2])
print(names[3])
```
  Frank
  Cece
  Justin
  Steph

### 3-2. Greetings
Start with the list you used in Exercise 3-1, but instead of just printing each person’s name, print a message to them. The text of each message should be the same, but each message should be personalized with the person’s name.
```python
names = ["Frank", "Cece", "Justin", "Steph"]
print(f"Hello {names[0]}, hello!")
print(f"Hello {names[1]}, hello!")
print(f"Hello {names[2]}, hello!")
print(f"Hello {names[3]}, hello!")



```
