---
layout: plain
title: Data Definition
---

## Modifying Schema 

### CREATE
The mapping of the term database is slightly different in Polypheny, as the databases used for MongoQL are mapped to 
Polypheny schemas. This means that commands normally executed on the term "database" are equivalent to operations executed 
on term schema in Polypheny.
To select a database the following command can be used. 
If the database does not already exist it gets generated automatically.

```use database```

Similarly to generate a collection the following command can be used. If a collection already exists this command is a no-op.

```db.createCollection( <name>, <options> )```

To generate a new view the following syntax is used, if the collection does not exist an error is thrown.

```db.createView( <view>, <source>, <pipeline>, <options> )```



### DROP

The following command removed the complete database, so it should be used with care.
```db.dropDatabase()```

To drop a specific collection and all its content the following command is used.
```db.collection.drop( <options> )```

### RENAME

To rename a collection use the following command.

```db.collection.renameCollection( <target>, <dropTarget> )```
