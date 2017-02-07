---
layout: default
title: SqlBulkCopy BulkCopyTimeout
permalink: sqlbulkcopy-bulkcopytimeout
---

{% include template-h1.html %}

## Description

Number of seconds maximum for a batch before it times out.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET BulkCopyTimeout value.
    bulkCopy.BulkCopyTimeout = 300;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}
