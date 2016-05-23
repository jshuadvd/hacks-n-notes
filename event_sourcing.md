# Event Sourcing
 
> [Promoted by Greg Young](https://cqrs.files.wordpress.com/2010/11/cqrs_documents.pdf)

> **Event Sourcing** is Functional, not Object-Oriented.

- Event Sourcing is a combination of an EventStore that uses [CQRS](https://en.wikipedia.org/wiki/Command%E2%80%93query_separation) (Command-Query Responsibility Segregation) and [DDD](https://en.wikipedia.org/wiki/Domain-driven_design) (Domain Driven Design)
- The input is a command which gets validated by a CommandHandler
- Then it outputs one or many events that are stored transactionally (bundled in a single commit).
- Then they are published on a message broker such as MassTransit so that subscribed event listeners (or Observers) can trigger their Projection Builders.
- There are no deletes. Only appending. If you want to change the state you keep adding events to look like if it had returned to a previous state.


### Pros

- Don't lose info (storing data has become very cheap!)
- Has to be recorded from Time 0.
- Based on the alpha-beta algorithm.
- You can use Event Sourcing to run smoke-tests.
- Can prevent **super-user (root) attacks**
- Event Sourcing is like **WORM drive *(Write Once, Read Many)***.
- Reports are easier to put together.

### Cons

- More boiler plate
- Slower to code
- Overkill for data that you don't care.

## EventStore

> The Event Store is a database designed to support Event Sourcing.

## Domain Driven Design

> DDD does Not have **CRUD** (Create Read Update Delete). Only *Create* and *Read*.

## CQRS

> Composed of Commands and Queries.

Commands should mutate. Queries should just read. Commands don't return anything. Queries don't mutate.

### Commands
> Commands should be imperative in their semantics. eg. "Purchase"

By being imperative the imply that the command can be rejected if an error occurs.

The command *payload* is just the necessary info needed to process that command, and not the entire DTO (Data Transfer Object).

Every command must get a UUID in the payload to know which item to interact with.

They are stored in a normalized way, ideally (3NF)

### Queries

They are stored in a denormalized way to minimize JOINs needed and speedup queries.

### Events

> Event is something that happened, therefor it can't be rejected.

- Events should be in past tense

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


## EventStore libraries

- [GetEventStore](https://geteventstore.com/) - JS library by Greg Young
- [NEventStore](https://github.com/NEventStore/NEventStore) - .Net library