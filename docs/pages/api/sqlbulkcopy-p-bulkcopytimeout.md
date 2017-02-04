---
layout: default
title: SqlBulkCopy BulkCopyTimeout
permalink: bulkcopytimeout
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

    // ...ColumnMappings & Options...
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}
