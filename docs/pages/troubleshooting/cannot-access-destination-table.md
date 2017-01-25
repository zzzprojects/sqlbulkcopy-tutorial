---
layout: default
title: SqlBulkCopy - Cannot access destination table 'TheDestinationTable'.
permalink: cannot-access-destination-table
---


{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='Cannot access destination table \'TheDestinationTable\'.' %}

### Example
{% highlight csharp %}
// Oops! The used destination name doesn't exists
string destinationName = "TheInvalidDestinationTable";

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        // ENSURE you specify a value to the DestinationTableName property.
        // ENSURE the value specified is not empty.
        bulkCopy.DestinationTableName = destinationName;

        bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
        bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}

## Solution

### Cause

- You provided an invalid table name.
- You provided an invalid schema name.
- The user doesn't have right on the table name.
- The user doesn't have right on the schema name.

### Fix

- ENSURE you specify a value to the DestinationTableName property.
- ENSURE the value specified is not empty.

### Example
{% highlight csharp %}
// ENSURE you specify a value to the DestinationTableName property.
// ENSURE the value specified is not empty.
bulkCopy.DestinationTableName = destinationName;
{% endhighlight %}
