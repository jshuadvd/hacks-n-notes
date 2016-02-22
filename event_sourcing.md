# Event Sourcing

> **Event Sourcing** is Functional, not Object-Oriented.

- Don't lose info (storing data has become very cheap!)
- Has to be recorded from Time 0.
- Based on the alpha-beta algorithm.


## Projection

> The history of the events is called **Projection**.

## Read-model 

> So we don't need to query the projection.

## Actor


## Bus trap

Using bus to send events can lead into the trap of leading to ping the server for more information than what the message bus sends you. To try to solve that you write a Controller to ask for more info to the server.

As the app features pile up, you tend to end up with a bunch of controllers.

