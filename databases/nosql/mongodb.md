# MongoDB

* stores JSON as BSON (binary JSON that interprets types. similar to protobuf)

![](/assets/Screen Shot 2018-01-06 at 11.32.35 AM.png)

* for performance, it is important to create indexes


## Replica Sets

> Are used for persistance, not for performance.

- consists on multiple nodes which contain a copy of the database.
- there is only one primary node and multiple secondary nodes.
- writes and reads only go to the primary.
- secondary nodes are only for backup

## Reference

* [blockchain on mongodb guide](https://hub.mongodb.com/blockchain-hub)
* [mongodb native driver nodejs](http://mongodb.github.io/node-mongodb-native/)