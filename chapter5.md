# Chapter 5 - Reducing Costs with Duck Typing

## Could you tell me about duck typing - what does that mean in the context of Ruby?

Duck type means that object is defined by its interface and not class if we can. We can expect that if an object implements the public interface it behaves in a certain way.

## Could you give me a real example of a duck - where could we use it?

Logging interface. For example, we can have Logger Class that assumes that all of the objects passed to it, responds to *log* method. It doesn't care what kind of class objects are as long as they respond to correct method.

## How could we find a duck in an application?

If we send objects of different classes to a method and expect the same result on them it might mean that we can use duck typing. Also whenever we see *kind_of?*, *is_of?*, *respond_to?* or switch statements that depend on the class of passed object.

## What could happen if we overuse the ducks?

We can start to change internal Ruby classes (monkey patching). Also sometimes benefits of using ducks are not worth the cost of finding and implementing the correct abstraction that can be fragile in the result.

## What does mean “polymorphism” in context of an object - example?

It means that different objects have the ability to respond to the same messages. The sender of those messages doesn't care about receiver class. Each receiver provides their own implementation given behavior.
For example Admin class and User class. Both of them can respond to the same messages like for example email.

## How can we share ducks behavior between different objects?

Objects share duck typing behavior by implementing the same interfaces ( Public method signatures). Additionally, classes can include modules that give them access to shared interfaces.
