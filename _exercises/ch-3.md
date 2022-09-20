---
layout: page
title: Exercises Ch. 3
description: Select exercises from Python Crash Course
---

# Python Crash Course Chapter 3

## 3-1. Names
Store the names of a few of your friends in a list called names. Print each person’s name by accessing each element in the list, one at a time.


```python
names = ["Thomas", "Yuma", "Ellis", "Etha"]
print(names[0])
print(names[1])
print(names[2])
print(names[3])
```

    Thomas
    Yuma
    Ellis
    Etha


## 3-2. Greetings
Start with the list you used in Exercise 3-1, but instead of just printing each person’s name, print a message to them. The text of each message should be the same, but each message should be personalized with the person’s name.


```python
names = ["Thomas", "Yuma", "Ellis", "Etha"]
print(f"Hello {names[0]}, how are you doing today?")
print(f"Hello {names[1]}, how are you doing today?")
print(f"Hello {names[2]}, how are you doing today?")
print(f"Hello {names[3]}, how are you doing today?")
```

    Hello Thomas, how are you doing today?
    Hello Yuma, how are you doing today?
    Hello Ellis, how are you doing today?
    Hello Etha, how are you doing today?


## 3-3. Your Own List
Think of your favorite mode of transportation, such as a motorcycle or a car, and make a list that stores several examples. Use your list to print a series of statements about these items, such as “I would like to own a Honda motorcycle.”


```python
modes_of_transportation = ["car", "bike", "skateboard", "boat"]
print(f"At some point in my life, I would love to own a {modes_of_transportation[0]}")
print(f"At some point in my life, I would love to own a {modes_of_transportation[1]}")
print(f"At some point in my life, I would love to own a {modes_of_transportation[2]}")
print(f"At some point in my life, I would love to own a {modes_of_transportation[3]}")
```

    At some point in my life, I would love to own a car
    At some point in my life, I would love to own a bike
    At some point in my life, I would love to own a skateboard
    At some point in my life, I would love to own a boat


## 3-4. Guest List
If you could invite anyone, living or deceased, to dinner, who would you invite? Make a list that includes at least three people you’d like to invite to dinner. Then use your list to print a message to each person, inviting them to dinner.


```python
dinner_invitees = ["Mike Tyson", "Ellis Brown", "Richard Townsend", "Ming Chow"]
print(f"Hello {dinner_invitees[0]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[1]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[2]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[3]}, would you like to join me for dinner soon?")
```

    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?


## 3-5. Changing Guest List
You just heard that one of your guests can’t make the dinner, so you need to send out a new set of invitations. You’ll have to think of someone else to invite.

- Start with your program from Exercise 3-4. Add a print() call at the end of your program stating the name of the guest who can’t make it.

- Modify your list, replacing the name of the guest who can’t make it with the name of the new person you are inviting.

- Print a second set of invitation messages, one for each person who is still in your list.


```python
dinner_invitees = ["Mike Tyson", "Ellis Brown", "Richard Townsend", "Ming Chow"]
print(f"Hello {dinner_invitees[0]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[1]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[2]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[3]}, would you like to join me for dinner soon?")

print(f"Oh no! {dinner_invitees.pop(0)} can not come to dinner, he's got to train for his fight!")
new_guest = "Joe Rogan"
dinner_invitees.append("Joe Rogan")

print(f"Hello {dinner_invitees[0]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[1]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[2]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[3]}, would you like to join me for dinner soon?")
```

    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Oh no! Mike Tyson can not come to dinner, he's got to train for his fight!
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Hello Joe Rogan, would you like to join me for dinner soon?


## 3-6. More Guests
You just found a bigger dinner table, so now more space is available. Think of three more guests to invite to dinner.

- Start with your program from Exercise 3-4 or Exercise 3-5. Add a print() call to the end of your program informing people that you found a bigger dinner table.
- Use insert() to add one new guest to the beginning of your list.
- Use insert() to add one new guest to the middle of your list.
- Use append() to add one new guest to the end of your list.
- Print a new set of invitation messages, one for each person in your list.


```python
dinner_invitees = ["Mike Tyson", "Ellis Brown", "Richard Townsend", "Ming Chow"]
print(f"Hello {dinner_invitees[0]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[1]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[2]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[3]}, would you like to join me for dinner soon?")

print("Hey folks, I have found a bigger dinner table. Let's have some more guests over for dinner!")

# adding a guest to the beginning of the list
dinner_invitees.insert(0, "Mark Sheldon")

# adding a guest to the middle of the list
middle = len(dinner_invitees) // 2
dinner_invitees.insert(middle, "Donald Trump")

# adding a guest to the end of the list
dinner_invitees.append("Wayne Rooney")

# new invitations to everyone
for invitee in dinner_invitees:
    print(f"Hello {invitee}, would you like to join me for dinner soon?")
```

    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Hey folks, I have found a bigger dinner table. Let's have some more guests over for dinner!
    Hello Mark Sheldon, would you like to join me for dinner soon?
    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Donald Trump, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Hello Wayne Rooney, would you like to join me for dinner soon?


## 3-7. Shrinking Guest List
You just found out that your new dinner table won’t arrive in time for the dinner, and you have space for only two guests.

- Start with your program from Exercise 3-6. Add a new line that prints a message saying that you can invite only two people for dinner.
- Use pop() to remove guests from your list one at a time until only two names remain in your list. Each time you pop a name from your list, print a message to that person letting them know you’re sorry you can’t invite them to dinner.
- Print a message to each of the two people still on your list, letting them know they’re still invited.
- Use del to remove the last two names from your list, so you have an empty list. Print your list to make sure you actually have an empty list at the end of your program.


```python

# exercise 3-6

dinner_invitees = ["Mike Tyson", "Ellis Brown", "Richard Townsend", "Ming Chow"]
print(f"Hello {dinner_invitees[0]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[1]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[2]}, would you like to join me for dinner soon?")
print(f"Hello {dinner_invitees[3]}, would you like to join me for dinner soon?")

print("Hey folks, I have found a bigger dinner table. Let's have some more guests over for dinner!")

# adding a guest to the beginning of the list
dinner_invitees.insert(0, "Mark Sheldon")

# adding a guest to the middle of the list
middle = len(dinner_invitees) // 2
dinner_invitees.insert(middle, "Donald Trump")

# adding a guest to the end of the list
dinner_invitees.append("Wayne Rooney")

# new invitations to everyone
for invitee in dinner_invitees:
    print(f"Hello {invitee}, would you like to join me for dinner soon?")

print("Sorry folks, I can only invite two people to dinner :(")

while len(dinner_invitees) != 2:
    print(f"Sorry {dinner_invitees.pop()}, you are no longer invited to dinner.")

for invitee in dinner_invitees:
    print(f"Hello {invitee}, you are still invited to dinner. See you then!")

del dinner_invitees[0]
del dinner_invitees[0]

print(dinner_invitees)
```

    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Hey folks, I have found a bigger dinner table. Let's have some more guests over for dinner!
    Hello Mark Sheldon, would you like to join me for dinner soon?
    Hello Mike Tyson, would you like to join me for dinner soon?
    Hello Donald Trump, would you like to join me for dinner soon?
    Hello Ellis Brown, would you like to join me for dinner soon?
    Hello Richard Townsend, would you like to join me for dinner soon?
    Hello Ming Chow, would you like to join me for dinner soon?
    Hello Wayne Rooney, would you like to join me for dinner soon?
    Sorry folks, I can only invite two people to dinner :(
    Sorry Wayne Rooney, you are no longer invited to dinner.
    Sorry Ming Chow, you are no longer invited to dinner.
    Sorry Richard Townsend, you are no longer invited to dinner.
    Sorry Ellis Brown, you are no longer invited to dinner.
    Sorry Donald Trump, you are no longer invited to dinner.
    Hello Mark Sheldon, you are still invited to dinner. See you then!
    Hello Mike Tyson, you are still invited to dinner. See you then!
    []


## 3-8. Seeing the World
Think of at least five places in the world you’d like to visit.

- Store the locations in a list. Make sure the list is not in alphabetical order.
- Print your list in its original order. Don’t worry about printing the list neatly, just print it as a raw Python list.
- Use sorted() to print your list in alphabetical order without modifying the actual list.
- Show that your list is still in its original order by printing it.
- Use sorted() to print your list in reverse alphabetical order without changing the order of the original list.
- Show that your list is still in its original order by printing it again.
- Use reverse() to change the order of your list. Print the list to show that its order has changed.
- Use reverse() to change the order of your list again. Print the list to show it’s back to its original order.
- Use sort() to change your list so it’s stored in alphabetical order. Print the list to show that its order has been changed.
- Use sort() to change your list so it’s stored in reverse alphabetical order. Print the list to show that its order has changed.


```python
locations = ["Nepal", "Kuwait", "Australia", "China", "Dominican Republic"]
print(locations)

print(sorted(locations))
print(locations)

print(sorted(locations, reverse=True))
print(locations)

locations.reverse()
print(locations)

locations.reverse()
print(locations)

locations.sort()
print(locations)

locations.sort(reverse=True)
print(locations)
```

    ['Iceland', 'South Africa', 'Australia', 'Alaska', 'Japan']
    ['Alaska', 'Australia', 'Iceland', 'Japan', 'South Africa']
    ['Iceland', 'South Africa', 'Australia', 'Alaska', 'Japan']
    ['Japan', 'Alaska', 'Australia', 'South Africa', 'Iceland']
    ['Iceland', 'South Africa', 'Australia', 'Alaska', 'Japan']
    ['Alaska', 'Australia', 'Iceland', 'Japan', 'South Africa']
    ['South Africa', 'Japan', 'Iceland', 'Australia', 'Alaska']
