# MongoDB

* stores JSON as BSON (binary JSON that interprets types. similar to protobuf)

![](/assets/Screen Shot 2018-01-06 at 11.32.35 AM.png)

* for performance, it is important to create indexes
* The maximum BSON document size in MongoDB is 16
MB.

## GridFS

> For files larger than 16 MB, MongoDB provides a
convention called GridFS, which is implemented by all
MongoDB drivers. GridFS automatically divides large data
into 256 KB pieces called chunks and maintains the
metadata for all chunks. GridFS allows for retrieval of
individual chunks as well as entire documents. For example, an application could quickly jump to a specific timestamp in a video. GridFS is frequently used to store large binary files such as images and videos directly in MongoDB, without offloading them to a separate filesystem


## Replica Sets

> Are used for persistance, not for performance.

- consists on multiple nodes which contain a copy of the database.
- there is only one primary node and multiple secondary nodes.
- writes and reads only go to the primary.
- secondary nodes are only for backup

## Reference

* [blockchain on mongodb guide](https://hub.mongodb.com/blockchain-hub)
* [mongodb native driver nodejs](http://mongodb.github.io/node-mongodb-native/)

## Sharding

* splits database in multiple replica sets for scalability.
