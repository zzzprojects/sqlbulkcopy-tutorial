---
layout: default
title: SqlBulkCopy EnableStreaming
permalink: enablestreaming
---

{% include template-h1.html %}

## Description

True to enable streaming for IDataReader object.

- Type: System.Boolean
- Default Value: false

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET EnableStreaming value.
    bulkCopy.EnableStreaming = true;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(reader);
}
{% endhighlight %}
