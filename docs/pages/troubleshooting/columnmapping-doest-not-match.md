---
layout: default
title: SqlBulkCopy - The given ColumnMapping does not match up with any column in the source or destination.
permalink: columnmapping-doest-not-match
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The given ColumnMapping does not match up with any column in the source or destination.' %}

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
