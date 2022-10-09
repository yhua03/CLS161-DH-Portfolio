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
print(f"{names[0]}, hello!")
print(f"{names[1]}, hello!")
print(f"{names[2]}, hello!")
print(f"{names[3]}, hello!")
```
    Frank, hello!
    Cece, hello!
    Justin, hello!
    Steph, hello!

### 3-3. Your Own List
Think of your favorite mode of transportation, such as a motorcycle or a car, and make a list that stores several examples. Use your list to print a series of statements about these items, such as “I would like to own a Honda motorcycle.”
```python
car_brands = ["Lamborghini", "Rolls Royce", "Bentley"]
print(f"I'd love to drive a {car_brands[0]}!")
print(f"I'd love to drive a {car_brands[1]}!")
print(f"I'd love to drive a {car_brands[2]}!")
```
    I'd love to drive a Lamborghini
    I'd love to drive a Rolls Royce
    I'd love to drive a Bentley


### 3-4. Guest List
If you could invite anyone, living or deceased, to dinner, who would you invite? Make a list that includes at least three people you’d like to invite to dinner. Then use your list to print a message to each person, inviting them to dinner.
```python

invitees = ["Cece", "Justin", "Steph"]
print(f" Hey {invitees[0]}, wanna come over for dinner?")
print(f" Hey {invitees[1]}, wanna come over for dinner?")
print(f" Hey {invitees[2]}, wanna come over for dinner?")
```
     Hey Cece, wanna come over for dinner?
     Hey Justin, wanna come over for dinner?
     Hey Steph, wanna come over for dinner?
     
### 3-5. Changing Guest List
You just heard that one of your guests can’t make the dinner, so you need to send out a new set of invitations. You’ll have to think of someone else to invite.
```python

invitees = ["Cece", "Justin", "Steph"]
print(f" Hey {invitees[0]}, wanna come over for dinner?")
print(f" Hey {invitees[1]}, wanna come over for dinner?")
print(f" Hey {invitees[2]}, wanna come over for dinner?")
print(f"{invitees[0]} can't make to dinner tonight, we gotta ask someone else to fill in the spot!")
invitees = ["Ray", "Justin", "Steph"]
print(f" Hey {invitees[0]}, wanna come over for dinner?")
print(f" Hey {invitees[1]}, wanna come over for dinner?")
print(f" Hey {invitees[2]}, wanna come over for dinner?")
```
     Hey Cece, wanna come over for dinner?
     Hey Justin, wanna come over for dinner?
     Hey Steph, wanna come over for dinner?
     Cece can't make to dinner tonight, we gotta ask someone else to fill in the spot!
     Hey Ray, wanna come over for dinner?
     Hey Justin, wanna come over for dinner?
     Hey Steph, wanna come over for dinner?
     
### 3-6. More Guests
You just found a bigger dinner table, so now more space is available. Think of three more guests to invite to dinner.
```python
invitees = ["Ray", "Justin", "Steph", "Cece"]
invitees.append("Mom", "Dad")
print(f" Hey {invitees[0]}, wanna come over for dinner?")
print(f" Hey {invitees[1]}, wanna come over for dinner?")
print(f" Hey {invitees[2]}, wanna come over for dinner?")
print(f" Hey {invitees[3]}, wanna come over for dinner?")
print(f" Hey {invitees[4]}, wanna come over for dinner?")
print(f" Hey {invitees[5]}, wanna come over for dinner?")
```

     Hey Ray, wanna come over for dinner?
     Hey Justin, wanna come over for dinner?
     Hey Steph, wanna come over for dinner?
     Hey Cece, wanna come over for dinner?
     Hey Mom, wanna come over for dinner?
     Hey Dad, wanna come over for dinner?
     
### 3-7. Shrinking Guest List
You just found out that your new dinner table won’t arrive in time for the dinner, and you have space for only two guests.
Start with your program from Exercise 3-6. Add a new line that prints a message saying that you can invite only two people for dinner.
Use pop() to remove guests from your list one at a time until only two names remain in your list. Each time you pop a name from your list, print a message to that person letting them know you’re sorry you can’t invite them to dinner.
Print a message to each of the two people still on your list, letting them know they’re still invited.
Use del to remove the last two names from your list, so you have an empty list. Print your list to make sure you actually have an empty list at the end of your program.
```python
invitees = ["Ray", "Justin", "Steph", "Cece", "Mom", "Dad]
print(f" Hey {invitees[0]}, wanna come over for dinner?")
print(f" Hey {invitees[1]}, wanna come over for dinner?")
print(f" Hey {invitees[2]}, wanna come over for dinner?")
print(f" Hey {invitees[3]}, wanna come over for dinner?")
print(f" Hey {invitees[4]}, wanna come over for dinner?")
print(f" Hey {invitees[5]}, wanna come over for dinner?")
print("Sorry, it turns out I can only invite two people to dinner")
print(f" Sorry {invitees.pop()}, you can no longer come to dinner")
print(f" Sorry {invitees.pop()}, you can no longer come to dinner")
print(f" Sorry {invitees.pop()}, you can no longer come to dinner")
print(f" Sorry {invitees.pop()}, you can no longer come to dinner")
print(f" Hey {invitees[0]}, you are still invited!'")
print(f" Hey {invitees[1]}, you are still invited!'")
del invitees[0]
del invitees[0]
print(invitees)
```

     Hey Ray, wanna come over for dinner?
     Hey Justin, wanna come over for dinner?
     Hey Steph, wanna come over for dinner?
     Hey Cece, wanna come over for dinner?
     Hey Mom, wanna come over for dinner?
     Hey Dad, wanna come over for dinner?
     Sorry, it turns out I can only invite two people to dinner
     Sorry Ray, you can no longer come to dinner
     Sorry Justin, you can no longer come to dinner
     Sorry Steph, you can no longer come to dinner
     Sorry Cecee, you can no longer come to dinner
     Hey Mom, you are still invited!
     Hey Dad, you are still invited!
     []
     
 ### 3-8. Seeing the World
 Think of at least five places in the world you’d like to visit.
 ```python
locations = ["Galapagos", "Italy", "Egypt", "Belize", "Indonesia"]
print(locations)

print(sorted(locations))

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
["Galapagos", "Italy", "Egypt", "Belize", "Indonesia"]
["Belize", "Egypt", "Indonesia", "Italy", "Galapagos"]
["Galapagos", "Italy", "Egypt", "Belize", "Indonesia"]
["Indonesia", "Belize", "Egypt", "Italy", "Galapagos"]
["Galapagos", "Italy", "Egypt", "Belize", "Indonesia"]
["Belize", "Egypt", "Indonesia", "Italy", "Galapagos"]
["Galapagos", "Italy", "Egypt", "Belize", "Indonesia"]
