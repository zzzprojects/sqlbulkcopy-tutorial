---
layout: default
title: SqlBulkCopy - The DestinationTableName property must be set before calling this method.
permalink: destinationtablename-property-must-be-set
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The DestinationTableName property must be set before calling this method.' %}

### Example
{% highlight csharp %}
// Oops! The destination name is empty
string destinationName = "";

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

- You never provided any value to the DestinationTableName property (empty by default).
- You provided an empty string to the DestinationTableName property.

### Fix

- ENSURE you provide value to the DestinationTableName property.
- ENSURE the value you provided is not empty.
