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
