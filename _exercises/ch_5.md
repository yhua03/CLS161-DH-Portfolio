---
layout: page
title: HW5 Python
description: HW5 Python
---

## _Python Crash Course_ Chapter 5


### 5-1. Conditional Tests
Write a series of conditional tests. Print a statement describing each test and your prediction for the results of each test. 


```python
obj = 'dog'
print("Is obj == 'dog'? I think it is.")
print(obj == 'dog')
print("\nIs obj == 'cat'? I don't think it is.")
print(obj == 'cat')

```
Is obj == 'dog'? I think it is.
True

Is obj == 'cat'? I don't think it is.
False

### 5-2. More Conditional Tests
You don’t have to limit the number of tests you create to 10. If you want to try more comparisons, write more tests and add them to `conditional_tests.py`. Have at least one `True` and one `False` result for each of the following:
- Tests for equality and inequality with strings
- Tests using the `lower()` function
- Numerical tests involving equality and inequality, greater than and less than, greater than or equal to, and less than or equal to
- Tests using the `and` keyword and the `or` keyword
- Test whether an item is in a list
- Test whether an item is not in a list

```python
mystring = "I love dogs"
print("Is mystring == 'I love dogs'? I think it is.")
print(mystring == 'I love dogs')
print("\nIs mystring == 'I love cats'? I don't think it is.")
print(mystring == 'I love cats')
```
Is mystring == 'I love dogs'? I think it is.
True

Is mystring == 'I love cats'? I don't think it is.
False

```python
mystring = "I love dogs"
print("Is mystring.lower() == 'i love dogs'? I think it is.")
print(mystring.lower() == 'i love dogs')
print("\nIs mystring == 'I Love Dogs'? I don't think it is.")
print(mystring.lower() == 'I Love Dogs')
```
Is mystring.lower() == 'i love dogs'? I think it is.
True

Is mystring == 'I Love Dogs'? I don't think it is.
False

```python
print("Is 3 * 3 == 10? No")
print(3 * 3 == 10)
print("Is 3 * 3 == 9? Yes")
print(3 * 3 == 9)
print("Is 3 * 3 > 10? No")
print(3 * 3 > 10)
print("Is 3 * 3 < 10? Yes")
print(3 * 3 < 10)
```
Is 3 * 3 == 10? No
False
Is 3 * 3 == 9? Yes
True
Is 3 * 3 > 10? No
False
Is 3 * 3 < 10? Yes
True

```python
print("Is 3 * 3 == 10 and 3 > 2 ? No")
print(3 * 3 == 10 and 3 > 2)
print("Is 3 * 3 == 9 and 3 > 2 ? No")
print(3 * 3 == 9 and 3 > 2)
```
Is 3 * 3 == 10 and 3 > 2 ? No
False
Is 3 * 3 == 9 and 3 > 2 ? No
True


### 5-6. Stages of Life

Write an `if-elif-else` chain that determines a person’s stage of life. Set a value for the variable `age`, and then:

- If the person is less than 2 years old, print a message that the person is a baby.
- If the person is at least 2 years old but less than 4, print a message that the person is a toddler.
- If the person is at least 4 years old but less than 13, print a message that the person is a kid.
- If the person is at least 13 years old but less than 20, print a message that the person is a teenager.
- If the person is at least 20 years old but less than 65, print a message that the person is an adult.
- If the person is age 65 or older, print a message that the person is an elder.


```python
age = 10
if age < 2:
    print("You are a baby.")
elif age >= 2 and age < 4:
    print("You are a toddler.")
elif age >=4 and age < 13:
    print("You are a kid.")
elif age >= 13 and age < 20:
    print("You are a teenager.")
elif age >=20 and age < 65:
    print("You are an adult.")
else:
    print("You are an elder")
```
You are a kid.

### 5-7. Favorite Fruit

Make a list of your favorite fruits, and then write a series of independent `if` statements that check for certain fruits in your list.

- Make a list of your three favorite fruits and call it `favorite_fruits`.
- Write five `if` statements. Each should check whether a certain kind of fruit is in your list. If the fruit is in your list, the `if` block should print a statement, such as "You really like bananas!"

```python
favorite_fruits = ["watermelon", "grape", "lime"]
if "banana" in favorite_fruits:
    print("You really like banans!")
    
if "watermelon" in favorite_fruits:
    print("You really like watermelons!")
    
if "grape" in favorite_fruits:
    print("You really like grapes!")
    
if "lemon" in favorite_fruits:
    print("You really like lemons!")
```

You really like watermelons!
You really like grapes!

### 5-8. Hello Admin

Make a list of five or more usernames, including the name 'admin'. Imagine you are writing code that will print a greeting to each user after they log in to a website. Loop through the list, and print a greeting to each user:

- If the username is 'admin', print a special greeting, such as "Hello admin, would you like to see a status report?"
- Otherwise, print a generic greeting, such as "Hello Eric, thank you for logging in again."

```python
usernames = ['admin', 'fhua', 'msaxton', 'yhua03', 'spongebob']
for username in usernames:
    if username == 'admin':
        print(f"Hello {username}, would you like to see a status report?")
    else:
        print(f"Hello {username}, thank you for logging in again.")
```

Hello admin, would you like to see a status report?
Hello fhua, thank you for logging in again.
Hello msaxton, thank you for logging in again.
Hello yhua03, thank you for logging in again.
Hello spongebob, thank you for logging in again.

