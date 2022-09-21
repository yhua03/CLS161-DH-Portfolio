---
layout: page
title: Exercises Ch. 5
description: Select exercises from Python Crash Course
---

## _Python Crash Course_ Chapter 5

### 5-1. Conditional Tests
Write a series of conditional tests. Print a statement describing each test and your prediction for the results of each test. 


```python
item = 'soccer ball'
print("Is item == 'soccer ball'? I predict True.")
print(item == 'soccer ball')

print("\nIs item == 'baseball'? I predict False.")
print(item == 'baseball')
```

    Is item == 'soccer ball'? I predict True.
    True
    
    Is item == 'baseball'? I predict False.
    False



```python
person = 'ankur'
print("Is person != 'ankur'? I predict False.")
print(person != 'ankur')

print("\nIs person == 'ankur'? I predict True.")
print(person == 'ankur')
```

    Is person != 'ankur'? I predict False.
    False
    
    Is person == 'ankur'? I predict True.
    True



```python
name = 'micah'
print("Is name == 'Micah'? I predict False.")
print(name == 'Micah')

print("\nIs name.title() == 'Micah'? I predict True.")
print(name.title() == 'Micah')
```

    Is name == 'Micah'? I predict False.
    False
    
    Is name.title() == 'Micah'? I predict True.
    True



```python
a, b = 5, 10
print("Is a > b? I predict False.")
print(a > b)

print("\nIs a < b? I predict  True.")
print(a < b)
```

    Is a > b? I predict False.
    False
    
    Is a < b? I predict  True.
    True



```python
a, b, c = 3, 4, 5
print("Is a + b > c? I predict True.")
print(a + b > c)

print("\nIs a > b + c? I predict False.")
print(a > b + c)
```

    Is a + b > c? I predict True.
    True
    
    Is a > b + c? I predict False.
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
# Tests for equality and inequality with strings
mystring = "Oh, what a day."
print("Is mystring == 'Oh, what a day.'? I predict True.")
print(mystring == 'Oh, what a day.')

print("\nIs mystring.upper() == 'Oh, what a day'? I predict False.")
print(mystring.upper() == 'Oh, what a day.')
```

    Is mystring == 'Oh, what a day.'? I predict True.
    True
    
    Is mystring.upper() == 'Oh, what a day'? I predict False.
    False



```python
# Tests using the lower() function
mystring = "Oh, what a day."
print("Is mystring.lower() == 'oh, what a day.'? I predict True.")
print(mystring.lower() == 'oh, what a day.')

print("\nIs mystring.lower() == 'Oh, what a day.'? I predict False.")
print(mystring.lower() == 'Oh, what a day.')
```

    Is mystring.lower() == 'oh, what a day.'? I predict True.
    True
    
    Is mystring.lower() == 'Oh, what a day.'? I predict False.
    False



```python
# Numerical tests involving equality and inequality, greater than and less than, greater than or equal to, 
# and less than or equal to
print("Is 50 == 3 * 30? I predict False.")
print(50 == 3 * 30)

print("\nIs 50 == 500 / 10? I predict True.")
print(50 == 500 / 10)

print("\nIs 1 != 2 - 1? I predict False.")
print(1 != 2 - 1)

print("\nIs 1 != 2? I predict True.")
print(1 != 2)

print("\nIs 50 > 500? I predict False.")
print(50 > 500)

print("\nIs 50 > 30? I predict True.")
print(50 > 30)

print("\nIs 50 < 30? I predict False.")
print(50 < 30)

print("\nIs 50 <= 51? I predict True.")
print(50 <= 51)

print("\nIs 50 >= 49? I predict True.")
print(50 >= 49)
```

    Is 50 == 3 * 30? I predict False.
    False
    
    Is 50 == 500 / 10? I predict True.
    True
    
    Is 1 != 2 - 1? I predict False.
    False
    
    Is 1 != 2? I predict True.
    True
    
    Is 50 > 500? I predict False.
    False
    
    Is 50 > 30? I predict True.
    True
    
    Is 50 < 30? I predict False.
    False
    
    Is 50 <= 51? I predict True.
    True
    
    Is 50 >= 49? I predict True.
    True



```python
# Tests using the and keyword and the or keyword
print("Is 50 == 50 and 20 == 1? I predict False.")
print(50 == 50 and 20 == 1)

print("\nIs 50 == 50 and 20 == 1 + 19? I predict True.")
print(50 == 50 and 20 == 1 + 19)

print("\nIs 50 == 50 or 20 == 1? I predict True.")
print(50 == 50 or 20 == 1)

print("\nIs 50 == 501 or 20 == 1? I predict False.")
print(50 == 501 or 20 == 1)
```

    Is 50 == 50 and 20 == 1? I predict False.
    False
    
    Is 50 == 50 and 20 == 1 + 19? I predict True.
    True
    
    Is 50 == 50 or 20 == 1? I predict True.
    True
    
    Is 50 == 501 or 20 == 1? I predict False.
    False



```python
# Test whether an item is in a list
friends = ["Ankur", "Yuma", "Ellis", "Thomas"]
print("Is 'Mia' in friends? I predict False")
print('Mia' in friends)

print("\nIs 'Yuma' in friends? I predict True.")
print('Yuma' in friends)
```

    Is 'Mia' in friends? I predict False
    False
    
    Is 'Yuma' in friends? I predict True.
    True



```python
# Test whether an item is not in a list
friends = ["Ankur", "Yuma", "Ellis", "Thomas"]
print("Is 'Mia' not in friends? I predict True")
print('Mia' not in friends)

print("\nIs 'Yuma' not in friends? I predict False.")
print('Yuma' not in friends)
```

    Is 'Mia' not in friends? I predict True
    True
    
    Is 'Yuma' not in friends? I predict False.
    False


### 5-6. Stages of Life

Write an `if-elif-else` chain that determines a person’s stage of life. Set a value for the variable `age`, and then:

- If the person is less than 2 years old, print a message that the person is a baby.
- If the person is at least 2 years old but less than 4, print a message that the person is a toddler.
- If the person is at least 4 years old but less than 13, print a message that the person is a kid.
- If the person is at least 13 years old but less than 20, print a message that the person is a teenager.
- If the person is at least 20 years old but less than 65, print a message that the person is an adult.
- If the person is age 65 or older, print a message that the person is an elder.


```python
age = 50
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

    You are an adult.


### 5-7. Favorite Fruit

Make a list of your favorite fruits, and then write a series of independent `if` statements that check for certain fruits in your list.

- Make a list of your three favorite fruits and call it `favorite_fruits`.
- Write five `if` statements. Each should check whether a certain kind of fruit is in your list. If the fruit is in your list, the `if` block should print a statement, such as "You really like bananas!"



```python
favorite_fruits = ["mango", "apple", "strawberry"]

if "banana" in favorite_fruits:
    print("You really like banans!")
    
if "apple" in favorite_fruits:
    print("You really like apples!")
    
if "orange" in favorite_fruits:
    print("You really like oranges!")
    
if "strawberry" in favorite_fruits:
    print("You really like strawberries!")
    
if "grape" in favorite_fruits:
    print("You really like grapes!")
```

    You really like apples!
    You really like strawberries!


### 5-8. Hello Admin

Make a list of five or more usernames, including the name 'admin'. Imagine you are writing code that will print a greeting to each user after they log in to a website. Loop through the list, and print a greeting to each user:

- If the username is 'admin', print a special greeting, such as "Hello admin, would you like to see a status report?"
- Otherwise, print a generic greeting, such as "Hello Eric, thank you for logging in again."


```python
usernames = ['admin', 'adahal', 'm_saxton', 'ebrown', '2cool4u']

for username in usernames:
    if username == 'admin':
        print(f"Hello {username}, would you like to see a status report?")
    else:
        print(f"Hello {username}, thank you for logging in again.")
```

    Hello admin, would you like to see a status report?
    Hello adahal, thank you for logging in again.
    Hello m_saxton, thank you for logging in again.
    Hello ebrown, thank you for logging in again.
    Hello 2cool4u, thank you for logging in again.


### 5-9. No Users

Add an `if` test to `hello_admin.py` to make sure the list of users is not empty.

- If the list is empty, print the message "We need to find some users!"
- Remove all of the usernames from your list, and make sure the correct message is printed.


```python
def greet_user(usernames):
    if len(usernames) != 0: # list is non-empty
        for username in usernames:
            if username == 'admin':
                print(f"Hello {username}, would you like to see a status report?")
            else:
                print(f"Hello {username}, thank you for logging in again.")
    else:
        print("We need to find some users!")

usernames = ['admin', 'adahal', 'm_saxton', 'ebrown', '2cool4u']
greet_user(usernames)

usernames.clear() # delete all items from list
greet_user(usernames)
```

    Hello admin, would you like to see a status report?
    Hello adahal, thank you for logging in again.
    Hello m_saxton, thank you for logging in again.
    Hello ebrown, thank you for logging in again.
    Hello 2cool4u, thank you for logging in again.
    We need to find some users!


### 5-10. Checking Usernames

Do the following to create a program that simulates how websites ensure that everyone has a unique username.

- Make a list of five or more usernames called `current_users`.
- Make another list of five usernames called `new_users`. Make sure one or two of the new usernames are also in the `current_users` list.
- Loop through the `new_users` list to see if each new username has already been used. If it has, print a message that the person will need to enter a new username. If a username has not been used, print a message saying that the username is available.
- Make sure your comparison is case insensitive. If 'John' has been used, 'JOHN' should not be accepted.


```python
current_users = ['admin', 'adahal', 'm_saxton', 'ebrown', '2cool4u']
current_users_lower = [user.lower() for user in current_users] # a copy of current_users with all lowercase usernames

new_users = ['newuser1', '2cool4u', 'm_saxton', 'niceuser123', 'god']

for user in new_users:
    if user.lower() in current_users_lower:
        print(f"{user} is not available, please choose a new username.")
    else:
        print(f"{user} is available.")
```

    newuser1 is available.
    2cool4u is not available, please choose a new username.
    m_saxton is not available, please choose a new username.
    niceuser123 is available.
    god is available.

