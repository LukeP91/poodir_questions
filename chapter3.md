# Chapter 3 - Managing Dependencies

## What is one way / two-way dependency between objects?

Test

## What can you do in order to lower dependencies?

We should break all dependencies between objects that are not necessary. Inject dependency, an object that implements an interface that you depend on.

## What kind of dependencies can be between objects?

* Class knows name of class it depends on and requires object of that specific class
* Class needs to know order of parameters of class it depends on
* Class knows names of parameters of class it depends on
* Class knows name of any method of class it depends on

## What does “injecting dependencies” mean?

Injecting dependency means passing as an argument to method or class initialization object of a class that we depend on. In Ruby object that has a method that we depend on, so-called "Duck typing".

## Tell me about isolating dependencies

* we can isolate creation of object ( either in initializer or separate method (lazy creation of dependent object))
* isolate call to an external message, from an object that we depend on. Pull method call to separate method
* remove argument order dependency on creating an object of a class that we depend on. You can use a hash to pass arguments and use default values
* use Wrapper(Factory/Facade) to hide arguments order when you can't change the class you depend on. An object from external API.

## Tell me about dependency direction

### Reversing dependency direction

You can change which object depends on which. For example instead of passing Wheel to Gear class so it can calculate gear ratio. You can you can change it so now Wheel needs an instance of Gear.

### How would you choose dependency direction?

* Depend on things that are less likely to change
* Depend on abstraction as those are more stable
* Specific implementations that can change often should not be dependent on in many places.

We can divide code based on two things ( how often it changes, and how much it is dependent on) and divide it into 4 groups:
* First one is code that changes often but is rarely dependent on
* Next code that changes rarely (is stable), but is dependent on often
* Code that doesn't change much and is not dependent on
* And the last one, most dangerous. Code that changes often and has lots of dependencies
