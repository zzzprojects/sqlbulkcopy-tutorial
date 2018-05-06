---
layout: default
title: SqlBulkCopy WriteToServerAsync
permalink: writetoserverasync
---

{% include template-h1.html %}

## Description

The asynchronous version of WriteToServer. Copy all rows from the source to the destination table.

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    bulkCopy.DestinationTableName = "TheDestinationTable";
    
    // CALL WriteToServerAsync method.
    bulkCopy.WriteToServerAsync(dt, cancellationToken);
}
{% endhighlight %}
