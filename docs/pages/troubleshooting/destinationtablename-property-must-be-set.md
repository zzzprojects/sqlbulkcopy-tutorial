---
layout: default
title: SqlBulkCopy: The DestinationTableName property must be set before calling this method.
permalink: destinationtablename-property-must-be-set
---

{% include template-h1.html %}

{% include begin-block-h2.html title='Problem' %}

<p>
The method WriteToServer throw the following error:
</p>

{% include template-exception.html message='The DestinationTableName property must be set before calling this method.' %}

{% include end-block-h2.html %}

{% include begin-block-h2.html title='Solution' %}

This error can be caused for two reasons:

- You never provided any value to the DestinationTableName property (The default value = empty)
- You provided an empty string value has been provided to the DestinationTableName property

How to Fix

- ENSURE the destination table name exist. Make a SELECT * FROM [TheDestinationTable] in SSMS
- ENSURE the user have right. Log with the user information into SSMS and make the SELECT * FROM [TheDestinationTable]

{% include begin-code.html %}
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
{% include end-code.html %}
{% include end-block-h2.html %}
