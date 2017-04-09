# Software Engineering/Programming Cheatsheet

## What's the difference between a method and a function?

A function is a piece of code that is called by name. It can be passed data to operate on (i.e. the parameters) and can optionally return data (the return value). All data that is passed to a function is explicitly passed.
- A function is independent of an object.

A method is a piece of code that is called by a name that is associated with an object. In most respects it is identical to a function except for two key differences:
1. A method is implicitly passed the object on which it was called.
2. A method is able to operate on data that is contained within the class (remembering that an object is an instance of a class - the class is the definition, the object is an instance of that data).
- A method is on an object.

Methods are functions that belong to a class, functions can be on any other scope of the code so you could state that **all methods are functions, but not all functions are methods**

i.e.
```python
class Door:
  def open(self):
  print 'hello stranger'
```

```python
def knock_door:
  a_door = Door()
  Door.open(a_door)

knock_door()
```

## What is the MVC framework? 

Basically what it is, is a way to organize your code into logical groupings that keep the various pieces separate and easily modifiable.

> Model = Data structure/data source. It's your database storage, it's the code needed to add/remove/update/change the information you warehouse.

> View = the part the user sees and interacts with. An HTML page, an application window.

> Controller = the code that marries the View to the Model. If you clicked a "Delete" button, it handles the business logic and rules (are you the authorized person to delete? is it a deletable record, etc).

i.e.
MVC can be metaphorically related to a TV. You have various channels, with different information on them supplied by your cable provider (the model). The TV screen displays these channels to you (the view). You pressing the buttons on the remote controls affects what you see and how you see it (the controller).

## What is a Class? What is inheritance? 

## Use the MVC framework to describe how a person views his hand (5 cards) from a deck of 52 cards.

## What is object oriented programming?
