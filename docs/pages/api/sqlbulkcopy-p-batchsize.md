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

If you need to INSERT 250 rows with a BatchSize of 100, 3 batchs will be sent to the server.

- Batch 1: 100 rows
- Batch 2: 100 rows
- Batch 3: 50 rows

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
	// SET the BatchSize.
	bulkCopy.BatchSize = 50;
	
	// ...code...
}
{% endhighlight %}
