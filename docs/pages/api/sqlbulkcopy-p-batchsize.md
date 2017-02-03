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

If you need to INSERT 250 rows with a BatchSize of 100, 3 batchs will be sent to the server
1. 100 rows
2. 100 rows
3. 50 rows

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
	// SET the BatchSize.
	bulkCopy.BatchSize = 50;
	
	// ...code...
}
{% endhighlight %}

## FAQ
- What is the recommanded batch size for SqlBulkCopy?

{% include end-block-h2.html %}

## Troubleshooting
{% include begin-block-h2.html title='Troubleshooting' %}
{% include end-block-h2.html %}
