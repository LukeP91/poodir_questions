# Chapter 2

## How can you group methods in a class?
By answering if those methods explain behavior or give access to properties of a certain object.
## Tell me about organizing code which is easy to change
Code that is easy to change can be defined as certain properties:
* Changes that are made have no unexpected side effects
* Small change in requirements should require small change in code
* Code should be easy to reuse
* It encourages that change that is being made is itself easy to change
## Tell me about the following qualities (TRUE):
Transparent - The consequences of change should be obvious in the code that is
changing and in distant code that relies upon it (don't know how to rephrase it)
Reasonable - required change should be
Usable - code should be easy to reuse
Exemplary - written code should promote good qualities and encourage others changing it to apply them
## How would you define a class which has a single responsibility?
It means that it does enough to be useful and nothing else. In other words, when we tread methods as orders that we can give or questions that we can ask about an object and they make sense it means that a class has a single responsibility. For example, let say we have a shop with books in it. It makes sense to ask book about its author or how many pages it has, but it's not a responsibility of a book to know if it is in a warehouse.
SRP doesn't mean that a class should do only one thing it simply means that everything it does is highly related to it.
## When you would decide to create a new class?
When certain methods that are contained in given class depend on the same parameter that is passed between them and they describe the behavior of one object. We also need to take into account cost of that change. If given class has no clear intention it could be misleading to other developers. But if we have not enough information and the cost of leaving the code is small. We should postpone the decision about changing it.
## What does that mean that method has a single responsibility?
It means that method should have only one reason to change.
## What do comments in code mean (from a design perspective)?
It can often mean that a method that the comment describes is not cohesive enough. If a certain part of methods requires commenting it can be extracted to a new method which name can work as a comment. Comments present risk of being outdated. Because they are not executable code there is no easy way to check if given comment is out of date.
