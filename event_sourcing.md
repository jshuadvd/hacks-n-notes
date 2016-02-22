# Event Sourcing

> **Event Sourcing** is Functional, not Object-Oriented.

1. Don't lose info (storing data has become very cheap!)
1. Has to be recorded from Time 0.
1. Based on the alpha-beta algorithm.
1. You can use Event Sourcing to run smoke-tests.
1. Can prevent **super-user (root) attacks**
1. Event Sourcing is like **WORM drive *(Write Once, Read Many)***.

## Projection

> The history of the events is called **Projection**.

## Read-model 

> So we don't need to query the projection.

### Snapshots

> To avoid replaying the whole Projection, you can create snapshots.

- Avoid snapshots if the Projection is short enough.

## Actor


## Bus trap

Using bus to send events can lead into the trap of leading to ping the server for more information than what the message bus sends you. To try to solve that you write a Controller to ask for more info to the server.

As the app features pile up, you tend to end up with a bunch of controllers.

