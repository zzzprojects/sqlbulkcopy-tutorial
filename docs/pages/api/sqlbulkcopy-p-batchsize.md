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

If you only have a few hundreds of rows, that's not an issue. But when you start to have thousands of row, you will start to lose some performance.

There is no BatchSize value which exists that will fit in all scenarios.

We recommend using a BatchSize value of around 5000

{% include template-example.html %} 
{% highlight csharp %}
    bulkCopy.BatchSize = 4000;
}
{% endhighlight %}

Why do we recommend a SqlBulkCopy BatchSize value of 4000?

- Not to low
- Not to high

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

