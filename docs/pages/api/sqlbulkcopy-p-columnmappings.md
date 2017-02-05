---
layout: default
title: SqlBulkCopy ColumnMappings
permalink: columnmappings
---

{% include template-h1.html %}

## Description

Mapping between the source and destination columns.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET ColumnMappings values.
    bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
    bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}
