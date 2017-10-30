# Chapter 8 - Combining Objects with Composition
## What does composition mean in object-oriented design?

Objects have no life outside objects that have them. Composition in OO means that we take some small objects and combine them into bigger more complex one. Our object communicates with parts its composed of via interfaces. Usually, these smaller objects have a specific role that they have.

## How composition is different from inheritance?

With inheritance you get delegation. Inheritance can be described as a  *is-a* type of relationship. It tells what kind of object it is. We can make big changes to object behavior by making small changes in their's superclass.

Composition describes a *has-a* relationship. We need to define delegations if we need them. It possible is a better solution because has fewer dependencies. We create small objects that are easy to reason about and then compose bigger one from them.

## Could you give me a real example of composition (outside of the book)?

Studies and specializations. We can create University and Technology university that differ only by specializations that each of them provides.

## In the book, they used the “Forwardable” module - why would you use it? Why in rails don't we use it?

*Forwardable* Ruby module provides methods *def_delegate* with which we can delegate methods to other objects.

In Rails *ActiveSupport* is included by default. *ActiveSupport* has method *delegate* that we can use.

## For what purpose would you use a factory in context of composition?

When we have an object that needs a specific set of composable objects created to be of a specific kind. Factory allows us to create set of objects by providing "configuration" that will be used to produce an object. A factory is an object that creates other objects.

## What’s the difference between aggregation & composition?

Composition means that contained objects don't exist independently outside their's container.

Aggregation means that objects that are inside aggregate can exist without it.
For example:
* Department can't exist outside University that it belongs to (Composition)
* Profesor can exist outside University it works for (Aggregation)
