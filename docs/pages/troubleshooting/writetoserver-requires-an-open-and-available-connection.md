---
layout: default
title: SqlBulkCopy - WriteToServer requires an open and available Connection. The connection's current state is closed.
permalink: writetoserver-requires-an-open-and-available-connection
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='WriteToServer requires an open and available Connection. The connection\'s current state is closed.' %}

### Example
{% highlight csharp %}
using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    // Oops! The connection has never been opened
    // connection.Open();

    foreach (DataTable dt in ds.Tables)
    {
        using (var bulkCopy = new SqlBulkCopy(connection))
        {

            bulkCopy.BatchSize = 4000;
            bulkCopy.DestinationTableName = "TheDestinationTable";
            bulkCopy.WriteToServer(dt);
        }
    }
}
{% endhighlight %}

## Solution

### Cause

- The connection is closed


### Fix

- ENSURE to open the connection
