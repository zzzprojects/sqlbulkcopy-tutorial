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
    // SET NotifyAfter value.
    bulkCopy.NotifyAfter = 4000;

    bulkCopy.SqlRowsCopied += (sender, args) => { /* code */ };

    // ...ColumnMappings & Options...
    bulkCopy.WriteToServer(reader);
}
{% endhighlight %}
