---
layout: default
title: SqlBulkCopy - Execution Timeout Expired. The timeout period elapsed prior to completion of the operation or the server is not responding.
permalink: timeout-expired
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='Execution Timeout Expired. The timeout period elapsed prior to completion of the operation or the server is not responding.' %}

{% include template-example.html %} 
{% highlight csharp %}
// Oops! The specified timeout may be a little bit to low!
bulkCopyTimeout = 1;

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.BulkCopyTimeout = bulkCopyTimeout;
        bulkCopy.DestinationTableName = destinationName;
        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}

## Solution

### Cause

- The bulk copy take more time to execute than the BulkCopyTimeout specified.

### Fix

- INCREASE the BulkCopyTimeout value (default = 30s).
- DECREASE the BatchSize value (default = unlimited).

> The bulkCopyTimeout is by batch, not for the whole bulk operation.
