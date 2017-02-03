---
layout: default
title: SqlBulkCopy DestinationTableName
permalink: destinationtablename
---

{% include template-h1.html %}

## Description

Name of the destination table.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
	// SET the BatchSize.
	bulkCopy.BatchSize = 50;
	
	// ...code...
}
{% endhighlight %}
