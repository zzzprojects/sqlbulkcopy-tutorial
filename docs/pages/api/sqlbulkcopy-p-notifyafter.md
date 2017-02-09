---
layout: default
title: SqlBulkCopy NotifyAfter
permalink: notifyafter
---

{% include template-h1.html %}

## Description

Number of rows to process before raising the SqlRowsCopied events.

- Type: System.Int32
- Default Value: 0 (None)

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET NotifyAfter value.
    bulkCopy.NotifyAfter = 4000;

    bulkCopy.SqlRowsCopied += (sender, args) => { /* code */ };

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(reader);
}
{% endhighlight %}
