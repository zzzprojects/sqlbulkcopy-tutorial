---
layout: default
title: SqlBulkCopy - The DestinationTableName property must be set before calling this method.
permalink: destinationtablename-property-must-be-set2
---

{% include template-h1.html %}

## Problem

{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The DestinationTableName property must be set before calling this method.' %}

---

## Solution

### Cause

This error can be caused for the following reasons:

-You never provided any value to the DestinationTableName property (The default value = empty)
-You provided an empty string value has been provided to the DestinationTableName property

### Fix

-ENSURE the destination table name exist. Make a SELECT * FROM [TheDestinationTable] in SSMS
-ENSURE the user have right. Log with the user information into SSMS and make the SELECT * FROM [TheDestinationTable]

{% include template-example.html title="BAD Example" %} 
{% highlight csharp %}
string destinationName = "TheDestinationTable";

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        // ENSURE the destination table name exist. Make a SELECT * FROM [TheDestinationTable] in SSMS
        // ENSURE the user have right. Log with the user information into SSMS and make the SELECT * FROM [TheDestinationTable]
        bulkCopy.DestinationTableName = destinationName;

        bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
        bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}
