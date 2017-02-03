---
layout: default
title: SqlBulkCopy EnableStreaming
permalink: enablestreaming
---

{% include template-h1.html %}

## Description

True to enable streaming for IDataReader object.

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
