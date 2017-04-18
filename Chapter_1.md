# Topics
- **Method vs Function**
- **The MVC**
- **Class, Inheritance**
- **OOP & using it during an interview**

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
# this is how a method works, declared inside a class
class Door:
  def open(self):
  print 'hello stranger'
```

```python
# this is how a function works, not declared inside a class
# this function also calls the method we defined inside our class 
def knock_door:
  a_door = Door()
  Door.open(a_door)

knock_door()
```

## What is the MVC framework? 

Basically what it is, is a way to organize your code into logical groupings that keep the various pieces separate and easily modifiable.

> Model = Data structure/data source. It's your database storage, it's the code needed to add/remove/update/change the information you warehouse - It acts as an interface between the database and the application (as a data object). It will handle validations, associations, transactions etc.

> View =  Displays output to the users - The part the user sees and interacts with. An HTML page, an application window. 

> Controller = The code that marries the View to the Model - It gathers and processes data. Handles code which does data selection and data messaging. If you clicked a "Delete" button, it handles the business logic and rules (are you the authorized person to delete? is it a deletable record, etc).

i.e.
MVC can be metaphorically related to a TV. You have various channels, with different information on them supplied by your cable provider (the model). The TV screen displays these channels to you (the view). You pressing the buttons on the remote controls affects what you see and how you see it (the controller).

## What is a Class? What is inheritance? 

A class is like a blueprint which you use to create objects. An object is an instance of a class - it's a concrete 'thing' that you made using a specific class.

i.e.
- A class is like the blueprint for a house. Using this blueprint, you can build as many houses as you like.
- Each house you build (or instantiate, in OO lingo) is an object, also known as an instance.
- Each house also has an address, of course. If you want to tell someone where the house is, you give them a card with the address written on it. That card is the object's reference.

Inheritance is the concept of one thing gaining the properties or behaviours of something else. To say A inherits from B, is saying that A is a type of B. A Bird inherits from Animal because a Bird is a type of Animal - it can do the same things, but a little more (or differently)!
i.e.
```javascript
// This is the Animal *Type*
function Animal() {};
Animal.prototype.eat = function () {
    alert("All animals can eat!");
};
```

```javascript
// Declaring a Bird *Type*
function Bird() {};
Bird.prototype = new Animal(); // Birds inherit from Animal
Bird.prototype.fly = function() {
    alert("Birds are special, they can fly!");
};
```

```javascript
// Create an instance of the Bird Type
var woodpecker = new Bird();
woodpecker.eat(); // This works because Bird inherits properties from Animal
woodpecker.fly(); // This works an important part of how Bird is different to Animal

// Let's check an instance of Animal now
var elephant = new Animal();
elephant.eat(); // This works
elephant.fly(); // Error occurs since only Birds have fly() in its prototype
```

## Using OOP, design a way to add cards from a deck of standard playing cards to your hand.

We'll need to start with a blueprint(s) or Class(es) so we can create objects and methods.

A good place to begin, is to figure out possible candidates for objects: game, player, hand, card, deck, suit, value. Out of these possible candidates we want to find ones that can be reused and are relative to the task at hand: **card, hand, deck**. These will be our classes. 

Since we want to **add cards** from a **deck** to our **hand**, cards are relatively passive in this interaction, we can create methods like `dealCard()` for a Deck class or `addCard()` for our Hand Class.

If we want to know what cards our hand consists of, a Card object will need instance variables to represent its value or suit. We'll also need methods like `getSuit()` and `getValue` so that it is possible to discover the suit and value from outside the class.

## What is object oriented programming? Why do we use it?

Object-oriented programming (OOP) is a programming paradigm based on the concept of "objects", which are data structures that contain data, in the form of fields, often known as attributes; and code, in the form of procedures, often known as methods.

OOP says that bringing together data and its behaviour in a single location makes it easier to understand how a program works. OOP is good when you have a fixed set of operations on things, and as your code evolves, you primarily add new things. This can be accomplished by adding new classes which implement existing methods, and the existing classes are left alone.

Another type of programming paradigm is **Functional** programming. Functional programming is a style of building the structure and elements of computer programs, that treats computation as the evaluation of mathematical functions and avoids changing-state and mutable data.

FP says that data and behavior are distinctively different things and should be kept separate for clarity. Functional languages are good when you have a fixed set of things, and as your code evolves, you primarily add new operations on existing things. This can be accomplished by adding new functions which compute with existing data types, and the existing functions are left alone.
