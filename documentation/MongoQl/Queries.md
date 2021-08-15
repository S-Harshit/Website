---
layout: plain
title: Queries
---

## Queries

The MongoDB Query Language comes with a powerful combination of queries commands.

### Count Queries
The following two commands both retrieve the same count of the filtered documents.

```
db.collection.count( <filter>, <options> )
db.collection.countDocuments( <filter>, <options> )
```

If the result does not need to be as accurate and can be estimated, the following commands is also supported

```db.collection.estimatedDocumentCount( <options> )```

### Simple Queries
When simple queries need to be exuted the follwing command can be used.
```db.collection.find( <filter>, <projection> )```

To directly limit the retrieved record to one the use the following.
```db.collection.findOne( <filter>, <projection> )```

## Complex Queries
If more complex queries need to be constructed one can use the following command, more in [Aggregation](Aggregation.md)
```db.collection.aggregate( <pipeline>, <options> )```

