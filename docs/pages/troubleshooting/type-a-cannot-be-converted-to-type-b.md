---
layout: default
title: SqlBulkCopy - The given value of type String from the data source cannot be converted to type int of the specified target column.
permalink: type-a-cannot-be-converted-to-type-b
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The given value of type String from the data source cannot be converted to type int of the specified target column.' %}

### Example
{% highlight csharp %}
// Oops! The destination name is null
string destinationName = null;

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.DestinationTableName = destinationName;
        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}

## Solution

### Cause

- You provided a null value to the DestinationTableName property.

### Fix

- ENSURE the value you provided is not null.
