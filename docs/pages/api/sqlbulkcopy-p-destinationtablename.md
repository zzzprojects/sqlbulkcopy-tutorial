---
layout: default
title: SqlBulkCopy DestinationTableName
permalink: sqlbulkcopy-destinationtablename
---

{% include template-h1.html %}

## Description

Name of the destination table.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET DestinationTableName value.
    bulkCopy.DestinationTableName = "TheDestinationTable";

    // ...ColumnMappings & Options...
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}
