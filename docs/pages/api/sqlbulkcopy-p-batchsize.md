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

## Recommendation
- SET a BatchSize value
- USE a Transaction

### SET a BatchSize value

The SqlBulkCopy BatchSize value we recommend is: **4000**

By default, SqlBulkCopy will process the operation in a single batch. If you have 100000 rows to copy, 100000 rows will be copied at once.

If you only have a few hundreds of rows, that's not an issue. But when you start to have thousands of rows:
- Decrease SqlBulkCopy performance
- Increase the chance to get a Timeout Expired exception
- Increase the chance to get an OutOfMemory exception
- Impact server performance

There is no BatchSize value which exists that will fit in all scenarios.


{% include template-example.html %} 
{% highlight csharp %}
    bulkCopy.BatchSize = 4000;
{% endhighlight %}

Why do we recommend a SqlBulkCopy BatchSize value of 4000?

- The value is not to high
- The value is not to low

You may find a lot of articles about the recommended batch size. Some people will recommand 1000, 2000, 5000, etc. but all will end up...

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

