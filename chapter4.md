# Chapter 4 - Creating Flexible Interfaces

## Tell me about communication patterns - what are costs/benefits of them?
## How would you define an interface for a class?

All methods that are defined within given class. They can be divided into two interfaces, Public and Private.

## Public interface vs Private interface - what’s the difference?

Public:
* tells us primary responsibility of class
* is intended to be used by others
* is stable ( doesn't change very often )
* is safe to depend on
* should be thoroughly tested

Private:
* contains implementation details
* should not be used by others
* can change very often
* unsafe to depend on
* should not be tested

## Why would you use a sequence diagram? What’s its purpose?

To model objects and messages passed between them. Give use simple tool to experiment with different designs, objects arrangments.

## Could you draw a simple sequence diagram between two classes?

## What’s the thing with “asking about what not how the object”?

It means that we should tell other objects what we need from them and not how to do something. We should trust other objects that they do their part. The rule "Ask don't tell".

## What’s the difference between private, public & protected ruby keywords?

*Public* - method is visible everywhere.

*Protected* - method can be called by explicit receiver self or instance of the same class, subclass or self

*Private* - can't be called with an explicit receiver. Must be called with implicit one, inside class or object.

In Ruby, every method can be changed to public. Private methods usually mean those that are the most unstable ones. Protected describe unstable methods. And the public should inform other users that those methods are stable and can be dependent on.

## What’s the law of Demeter? How is it related to ruby objects & methods?

It means that we should call methods only from closest members. In other words, don't call methods of objects that you get from calling another object. In Ruby, we sometimes call it "Use only one dot".

It is allowed if your call receiver is of the same type as the caller. Like chaining methods that operate on Enumerable. If the returned value is of the same type.

## What can happen if we violate the law of Demeter?

It can force a change in unrelated parts of the code. It usually creates bigger coupling between objects, so they are harder to reuse. It often encourages or even forces to write similar code elsewhere, which increases coupling even more.

## How can we avoid violating Law of Demeter?

The easiest way is to use a delegate, but it often only hides the problem. It can be changed by fixing the design. Ask what information our object needs and design messages that it will send. Based on that design objects that will be called.
