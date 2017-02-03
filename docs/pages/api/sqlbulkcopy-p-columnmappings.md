---
layout: default
title: SqlBulkCopy ColumnMappings
permalink: columnmappings
---

{% include template-h1.html %}

## Description

Mapping between the source and destination columns.

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
