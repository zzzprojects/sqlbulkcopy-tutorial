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

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString, transaction))
{
    // SET BatchSize value.
    bulkCopy.BatchSize = 4000;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}

## Recommendation
- SET a BatchSize value
- USE a Transaction

### SET a BatchSize value

 - Recommended BatchSize Value: **4000**
 
{% include template-example.html %} 
{% highlight csharp %}
bulkCopy.BatchSize = 4000;
{% endhighlight %}

By default, SqlBulkCopy will process the operation in a single batch. If you have 100000 rows to copy, 100000 rows will be copied at once.

Not specifying a BatchSize can impact your application:

- Decrease SqlBulkCopy performance
- Increase the chance to get a Timeout Expired exception
- Increase the chance to get an OutOfMemory exception
- Impact server performance
- Impact database server performance

#### Why do we recommend a SqlBulkCopy BatchSize value of 4000?

- The value is not to high
- The value is not to low

There is no value that fit all scenarios. Some people will recommend a BatchSize of 1000, 2000, or 5000 and they are all good values which fit in the rule "not to high, not to low". All these value will have slighty performance difference which is sometime better or worse.

### Use a Transaction

- We recommend to use your transaction

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString, transaction))
{
   // ...code...
}
{% endhighlight %}


By default, SqlBulkCopy do not use a transaction. So if a batch fail, there is no rollback of all rows already processed from previous batch.

If you set the UseInternalTransaction option to true, a transaction will be created for every batch. Again, if a batch fail, there is no rollback of all rows already processed from previous batch.

The best solution, is creating your own transaction.
