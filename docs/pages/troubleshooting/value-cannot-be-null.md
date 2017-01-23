---
layout: default
title: SqlBulkCopy - Value cannot be null.
permalink: value-cannot-be-null
---


{% include template-h1.html %}

{% include begin-block-h2.html title='Problem' %}

<p>
The method WriteToServer throw the following error:
</p>

{% include template-exception.html message='Value cannot be null.' %}

{% include end-block-h2.html %}

{% include begin-block-h2.html title='Solution' %}

This error can be caused for the following reasons:

- You provided an invalid table name.
- You provided an invalid schema name.
- The user doesn't have right on the table name.
- The user doesn't have right on the schema name.

How to Fix

- ENSURE you specify a value to the DestinationTableName property.
- ENSURE the value specified is not empty.

{% include begin-code.html %}
{% highlight csharp %}
string destinationName = "TheDestinationTable";

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
{% include end-code.html %}
{% include end-block-h2.html %}
