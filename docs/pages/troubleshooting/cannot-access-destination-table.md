---
layout: default
title: SqlBulkCopy - Cannot access destination table
permalink: cannot-access-destination-table
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='Cannot access destination table \'[TheInvalidTableName]\'.' %}

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
- The user doesn't have right on the schema name.
- The user doesn't have right on the table name.

### Fix

- ENSURE the schema name is valid.
- ENSURE the table name is valid.

If the schema and table name was already valid and you still have the error:
- LOG into SSMS with the user/password used by the application and perform a SELECT statement to ensure he has access to it.
