---
layout: default
title: SqlBulkCopy EnableStreaming
permalink: sqlbulkcopy-enablestreaming
---

{% include template-h1.html %}

## Description

True to enable streaming for IDataReader object.

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
