---
layout: plain
title: Data Manipulation
---

## Modifying Data

### INSERT
To insert data into a specific collection/table, two different commands are supported.
To insert multiple records at ones the following command is used.

```db.collection.insertMany( <array> )```

Beside inserting multiple records at ones, the following command is also able to handle single records on insert.

```db.collection.insert( <document>|<array> )```


### DELETE
To remove the content of a collection the following syntax is used, it limits the delete records to a single one.

```db.collection.deleteOne( <filter> )```

If multiple records should be delete the appropriate command is as follows.

```db.collection.deleteMany( <filter> )```

Additionally, a less restrictive command is given with the following.
```db.collection.findOneAndDelete( <filter>, <options> )```

### UPDATE
Polypheny is able to support most available update combination, which are the following.

```
db.collection.findAndModify( <filter> )
db.collection.findOneAndReplace( <filter>, <replacement>, <options> )
db.collection.findOneAndUpdate( <filter>, <replacement>, <options> )
db.collection.replaceOne( <filter>, <replacement>, <options> )
db.collection.update( <query>, <update>, <options> )
db.collection.updateOne( <filter>, <update>, <options> )
db.collection.updateMany( <filter>, <update>, <options> )
```
