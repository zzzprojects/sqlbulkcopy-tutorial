---
layout: default
title: SqlBulkCopy - The given value of type String from the data source cannot be converted to type int of the specified target column.
permalink: type-a-cannot-be-converted-to-type-b
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The given value of type String from the data source cannot be converted to type int of the specified target column.' %}

{% include template-example.html %} 
{% highlight csharp %}
var dt = new DataTable();
dt.Columns.Add("TheColumnInt");
dt.Columns.Add("TheColumnString");

for (int i = 0; i < 100; i++)
{
    // Oops! The value added for "TheColumnInt" is empty
    dt.Rows.Add("", i);
}

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
        bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

        bulkCopy.BatchSize = 4000;
        bulkCopy.DestinationTableName = "TheDestinationTable";
        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}

## Solution

### Cause

- You provided an empty value which cannot be converted to another type.

### Fix

- ENSURE provided value is valid for the destination type.
- CREATE column by specifying the type to get the error before executing WriteToServer method.

### Example
{% highlight csharp %}
var dt = new DataTable();
dt.Columns.Add("TheColumnInt", typeof(int));
dt.Columns.Add("TheColumnString", typeof(string));
{% endhighlight %}
