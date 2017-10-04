# Chapter 1 - Object-Oriented Design

## What’s the difference between object oriented and functional programs?

**A functional programming language is a language that emphasizes programming with pure functions and immutable data. In functional programs data and behavior (functions) are separated.**
Pure function means that for the same data passed as function's arguments output will always be the same. So calling a function *f* twice with the same value for an argument *x* will produce the same result *f(x)* each time. In addition, pure functions don't cause side effects (changes in state that are not connected to input).
Immutable data means that functional programs do not have assignment statements, that is, the value of a variable in a functional program never changes once defined.

**In object-oriented languages data and behavior is combined with a single thing called *Object*.**
In OO languages objects talk with each other by sending messages and respond to messages by invoking one of their's methods.
In Ruby and other OO languages, we can define blueprints for creating new objects that are called classes. A class defines methods (definitions of behavior) and attributes (definitions of variables).
It's also important that each object encapsulates, or hides, its data from the world. Every object decides for itself how much, or how little, of its data to expose.

## What kind of problems does design solve?

Since most programs that we write are not *static*. And since something, somewhere will change design helps us prepare for that. Being ready for change is the most important part of designing applications. Correctly designed applications are easier and cheaper to change and maintain. Nicely designed programs should be flexible and adaptable.

## When we don’t have a design, what kind of challenges can we meet?

Poorly designed applications make each change more expensive both to introduce and maintain. Also, every new change makes next one event harder and more costly. In poorly designed application change in one place can cause cascading changes in unrelated parts of the code. Parts of the code are harder to re-use and test.

## How would you define “a process of design your code” in context of software?

The process of code design means a couple of things. First and foremost it's code arrangement. Two different programmers could solve the same problem and arrange code differently.
Object-oriented design is about *managing dependencies*. Since OO programs are made up of parts called objects that interact with each other by sending messages. And since we need to send the correct message to correct object, it created a dependency between sender and receiver that may stand in a way of change.
Design needs to not only deliver what is needed today but also plan for future requirements and changes. It doesn't mean that we should try to predict what will be needed next. It means that we should reduce the cost of changes.


## Could you talk about the design principles (SOLID)?
### Single Responsibility Principle
It states that each class should have only one reason to change or in other words, each class should have only one job.
### Open-closed
It means that class should be easy to extend without changing the class itself by adding new features through inheritance.
### Liskov Substitution (substitution of types)
It means that if a code uses a class that is a subclass of another class it should also work with the base class.
### Interface segregation
Interfaces should be as small as possible and expose only necessary things.
### Dependency Inversion (dependency on abstractions, not low level)
We should depend on abstraction and not a concrete implementation. In example when we have an object that we want to save in DB. It should not depend on an implementation of concrete database connector but rather on generic DB connector.
### Another two are
#### DRY - Don’t Repeat Yourself
We should write code that is reusable, which helps us with later changes. Since change will need to be made only in one place.
#### Law of Demeter (limited knowledge)
It means that each object should know as little as possible about other objects. And should send messages only to its closest collaborators. We want to tell our neighbors what we need and let them call other objects.

## What is a design pattern, and why would you use design patterns?

Design patterns are simple solutions to specific problems in OO software design. Each of design patterns names a common problem and gives you a blueprint how to solve it. Design patterns give programmers way in which they can communicate and collaborate.
