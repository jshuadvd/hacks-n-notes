# CQRS Event Sourcing

> **[CQRS](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation)** Command-Query Responsibility Segregation

> **Event Sourcing** is Functional, not Object-Oriented.


### Pros

- Don't lose info (storing data has become very cheap!)
- Has to be recorded from Time 0.
- Based on the alpha-beta algorithm.
- You can use Event Sourcing to run smoke-tests.
- Can prevent **super-user (root) attacks**
- Event Sourcing is like **WORM drive *(Write Once, Read Many)***.

### Cons

- More boiler plate
- Slower to code
- Overkill for data that you don't care.

## Projection

> The history of the events is called **Projection**.

The Projection is the left-fold or the result of the last state mutated by the last event handler. This result can be stored in a row in a database table. The result can be a json blob of the state at that point of time.

## Projection builder

> A Projection Builder runs the events and returns the left-fold.

## Read-model 

> So we don't need to query the projection.


### Snapshots

> To avoid replaying the whole Projection, you can create snapshots.

- Avoid snapshots if the Projection is short enough.

Snapshots is an optimization that can be done in case the queries are taking too long. You can do snapshots every X amount of events. Or if you get to a high volume of projection instances then you might just make a snapshot for the last state.



## Actor

What is an actor?

## Bus trap

Using bus to send events can lead into the trap of leading to ping the server for more information than what the message bus sends you. To try to solve that you write a Controller to ask for more info to the server.

As the app features pile up, you tend to end up with a bunch of controllers.


## Left Fold

The result from chaining methods.
Which each method comes from an event.

```javascript
var leftfold = compute(compute(compute()));
```

## Contracts

> A *contract* is a convention to set commands that mutate state and queries that are immutable, hence eliminating side-effects.

