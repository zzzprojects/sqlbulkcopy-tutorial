---
layout: default
title: SqlBulkCopy SqlRowCopied
permalink: sqlrowscopied
---

{% include template-h1.html %}


## Description
Even raised after the number of row in the NotifyAfter has been processed.

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
