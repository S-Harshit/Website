---
layout: plain
title: Aggregation Pipeline
---

The aggregation command with its aggregation pipeline is an extremely powerful tool to easily construct even complex queries.

## Example

```
db.secrets.aggregate([
    {
        "$match": {
            "example": 15
        }
    }, 
    {
        "$project": {
            "other": 1
        }
    }
])
```

The example aggregation query, first filters records from the collection/table named "secrets", for which "example" is equal to 15.
Then it applies a projection on the field/column named "other", which is shown in then shown as a result.

## Stages
The MongoDB Query Language supports different possible pipeline stages, which are described here for Polypheny.

### ```$addFields```

Adds a new field to the existing record.

### ```$count```

Counts the results up to this point and returns a single result.

### ```$group```

Groups the record by a needed ```_id``` field, and additionaly allows to speicify other aggregations.

### ```$limit```

Limits the retrieved records to the given amount of records.

### ```$match```

Filters the previous stage with the provided condition.

### ```$project```

Allows to apply a inclusive or exclusive projection to the records.

### ```$replaceRoot```

This is also an alias for ```$replaceWith``` and allows to replace a document with one of its subfields 

Attention: This stage is only possible when using a document schema.

### ```$set```

Is an alias for ```$addFields```, which allows to add adiditional entry during retrieval to an existing record.

### ```$skip```

Skips the specified amount of records.

### ```$sort```

Allows to sort by the given entities.

### ```$unset```

Is an alias for multple exlusive projections.

### ```$unwind```

Allows to deconstruct an array into multiple records for each entry.

Attention: This stage is only possible when using a document schema.
