---
layout: default
title: SqlBulkCopy DestinationTableName
permalink: destinationtablename
---

{% include template-h1.html %}

## Description

Name of the destination table.

- Type: System.Int32
- Default Value: String.Empty

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
