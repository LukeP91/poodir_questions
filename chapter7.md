# Chapter 7 - Sharing Role Behavior with Modules
## How could we define a role for an object - how does it differ from an “inheritance type” of an object?

The role is a behavior that unrelated classes share between them. They do not have the same superclass. In Ruby, we can mix in such roles using modules.

## What is the Liskov Substitution principle about? How does it correspond to duck typing?

A subtype can be used in place of its superclass. An object that includes a module can be interchanged with other object implementing what module.

## When would we share behavior using modules?

When we need to make sure that unrelated in other way objects behave the same. When we need objects to implement the same interface.

## What is the cost of using a lot of modules?

* it increases amount of methods that object has access to
* it makes finding method harder
* we can override one of the methods implemented in one of the modules with method implemented in another module.

## What antipatterns could we find when we overuse inheritance?

* we can create subclasses that don't change existing code
* we need to check which method to call based on class of object
* subclasses that don't use some of the superclass interfaces and return do not implement

## How would you extract part of the behavior of classes into a separate module?

First, implement it in one of the classes. Next, pull out all of the abstraction to separate module. If some methods or properties need to be changed in an object. Implement it in class and provide default behavior for such methods and properties in a module.
