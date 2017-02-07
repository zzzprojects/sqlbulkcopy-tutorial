---
layout: default
title: SqlBulkCopy WriteToServerAsync
permalink: sqlbulkcopy-writetoserverasync
---

{% include template-h1.html %}

## Description

The asynchronous version of WriteToServer. Copy all rows from the source to the destination table.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    bulkCopy.DestinationTableName = "TheDestinationTable";
    
    // CALL WriteToServerAsync method.
    bulkCopy.WriteToServerAsync(dt, cancellationToken);
}
{% endhighlight %}
