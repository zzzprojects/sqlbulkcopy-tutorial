---
layout: default
title: SqlBulkCopy BatchSize
permalink: batchsize
---

{% include template-h1.html %}

## Description
Number of rows for a batch.

- Type: System.Int32
- Default Value: 0 _(Unlimited)_

By default, SqlBulkCopy will process the operation in a single batch.





If you need to INSERT 250 rows with a BatchSize of 100, 3 batchs will be sent to the server.

- Batch 1: 100 rows
- Batch 2: 100 rows
- Batch 3: 50 rows


## Recommendation
- SET a BatchSize value of around 5,000 (not to low, not to high!)
- USE a Transaction if you specify a BatchSize

### SET a BatchSize
By default, SqlBulkCopy will process the operation in a single batch.

That's not an issue if you process only a hundred or row but when you process millions of row, you will lose a lot of performance.

### Use a Transaction
By default, SqlBulkCopy do not use a transaction.

If set UseInternalTransaction option to true, a transaction will be created for every batch, which is not the optimized solution either.

The best solution, is creating and handling yourself the transaction.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET BatchSize value.
    bulkCopy.BatchSize = 4000;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}

