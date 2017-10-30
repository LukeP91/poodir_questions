# Chapter 6 - Acquiring Behavior Through Inheritance
## When could we go for inheritance?

When we have a couple of classes from which we can extract common behavior. We should not create superclass when currently there is only one class that would inherit from it and try to guess abstraction.

## How could we refactor several classes into an inheritance structure?

1. Create empty "abstract" class that will be a superclass for all of those classes.
2. Promote shared part of the code to the parent class.
3. All required methods that should be overwritten in child classes that don't have default behavior should raise *NotImplementedError*.

## What is the issue when an inheritance structure has too many levels?

Inheritance can be either too wide or too deep. Problematic are deep inheritances with multiple levels. First, because they create long lookup paths for method delegation, which can be accidentally overwritten in one of the middle classes. Second, because usually, programmers have good knowledge about outside classes(classes at boundaries).

## What can happen if you use inheritance for the wrong case, e.g. when classes share only small part of common behavior?

It creates unnecessary coupling between classes. Doesn't provide a lot of benefits when only smart part of the code is reused. It is better to use modules in such case. Since classes can only have one parent it might turn out later that there would be a much better superclass, which now is harder to implement.

## Why would we go for a template method pattern -> example?

* when we need to have default behavior for all classes that only some will change
* to inform which method should be overwritten by child class ( by raising *NotImplementedError*)

## How can we lower dependency between a superclass and its children?

We can use hook messages. It allows hiding algorithm inside superclass. Hook messages are methods that should be implemented by a child class. For example by using *post_initialize* we allow child class to specify what extra information it needs during initialization. We hide how initialization looks like. That message can be sent at any time not necessarily during object initialization.
