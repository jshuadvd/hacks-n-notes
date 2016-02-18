# Event Sourcing

Projection TK

Read-model TK

## Bus trap

Using bus to send events can lead into the trap of leading to ping the server for more information than what the message bus sends you. To try to solve that you write a Controller to ask for more info to the server.

As the app features pile up, you tend to end up with a bunch of controllers.

