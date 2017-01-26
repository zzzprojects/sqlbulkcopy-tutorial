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
// Oops! The table name is invalid
string destinationName = "[TheInvalidTableName]";

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

- You provided an invalid schema name.
- You provided an invalid table name.
- The user doesn't have the right to the schema name.
- The user doesn't have the right to the table name.

### Fix

- ENSURE the schema name is valid.
- ENSURE the table name is valid.

If the schema and table name was already valid:

- LOG into SSMS with the user/password used by the application and perform a SELECT statement to ensure he has access to it.
