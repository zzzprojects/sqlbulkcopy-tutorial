---
layout: default
title: SqlBulkCopy NotifyAfter
permalink: notifyafter
---

{% include template-h1.html %}

## Description

Number of rows to process before raising the SqlRowsCopied events.

something else...

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
