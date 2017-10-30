# Chapter 9 - Designing Cost-Effective Tests
## What is the real purpose of tests?

To reduce the cost of maintaining software. They give us ways to find bugs, provide documentation, allow us to defer design decisions, support abstractions and expose design flaws.

## How would you test an object?

Test only that what is accessible from outside. Test only public interfaces of objects and in special cases outgoing messages.

## What messages should we test - incoming/outcoming?

We should always test incoming messages and outcoming only in specific cases. We should test only those outgoing messages that have side effects, like saving file.

Some rules:
* test incoming messages for state they return
* test outgoing command messages if they are being sent
* don't test outgoing query messages

## Tell me about BDD / TDD

BDD(outside-in) - we test boundaries of our application, expected behavior on a higher level and go down.

TDD(inside-out) - we test domain objects and then use them to create higher level logic.

## What can we use in order to isolate object under the test? e.g. classes/doubles - what are the pros/cons of them?

If a method of an object depends on other classes to perform it action there are two ways in which we can test them. We can use original classes that are needed and inject them. Such way makes our test closer to reality since we are using the same objects that our production code uses. The major con of it is that if an injected class is slow to initialize we are impacting significantly tests of our object under test. Since we want our unit tests to be fast there is a risk they will slow down significantly.
Another way to mitigate that issue is to use test doubles. Objects that pretend to object that we need that is often much faster to create. By using them we still prove that our object works correctly but we are not having the risk of lowering our test suite. Also, our doubles can return exactly what we want when the method is called which allows us to validate behavior under know state of our env. The major con of using doubles is that if we don't check if they use the same interface as an object that normally plays they role there is a risk that we will receive false positives. When for example method signature for a role that our double is playing changes we will not see it in our tests.

## What do you think about testing private methods? Why / Why not?

Since they are not visible from outside the object that calls them and can often change. There is little to be gained from testing them and writing tests for such methods only make changes harder to make. So we should not test them.

## What would you do with a lot of private methods of an object? Would you test them / extract into an object / inline them?

Ideally, private methods should not be tested since they are not part of the public interface that is exposed. If class has a lot of private methods there is a couple of things that can be done with them. We can inline them into public methods that are already tested. Another way is extracting part of those private methods to other class. Since having a lot of private methods can suggest that our class has more than one responsibility. And since now those methods are part of the public interface of other class we should test them. There is a risk however that those methods can still change a lot.

## What does it mean “testing outgoing messages”?

First, we should not test query messages. Testing outgoing messages should only be done if calling that message has some side effect that needs to occur. In such case, we should only test if a proper message is called when needed.

## What is a query message? Why / why not to test it?

The query message is an outgoing message that is sent to the receiver and returns some part of it state as has no side effect. Such messages should not be tested inside sender tests. They should be tested as incoming messages for the receiver.

## What is a command message? Why / why not to test it?

The command message is an outgoing message that has some form of side effect. For example, it saves current state to the database. In such case, we should check if such message was sent because the flow of our application depends on that fact.

## How can you test a duck type - modules which share common behavior?

We can create a class that will implement that module and not change its behavior and then tests that class if behavior provided by that module is correct.

## Should we test our doubles? Why / why not?

We should verify in some way that our doubles implement the correct interface and play the correct role. There is a risk that when we don't check our doubles they can use different interface that original object that will implement given role and return false positives. For example, we can change method signature and since we are testing using doubles we won't notice it. Another way to test it is to use integration tests that use real objects.

## How would you test inherited methods?

First, we should test if our subclass honors their contract and correctly implement the shared interface. We can write tests that verify that common behavior and then reuse them inside our subclasses.
