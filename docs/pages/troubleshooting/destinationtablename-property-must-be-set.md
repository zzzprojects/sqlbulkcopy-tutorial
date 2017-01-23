---
layout: default
title: SqlBulkCopy - The DestinationTableName property must be set before calling this method.
permalink: destinationtablename-property-must-be-set
---

{% include template-h1.html %}

<div class="card">
  <div class="card-header">
     <h2>Problem</h2>
  </div>
     <div class="card-block">
{% include template-execute-thrown.html methodName='WriteToServer' %}

{% include template-exception.html message='The DestinationTableName property must be set before calling this method.' %}
     </div>
</div>

<br /><br />
<hr>
<br /><br />

<div class="card">
  <div class="card-header">
     <h2>Solution</h2>
  </div>
  <div class="card-block">
     <h3 class="card-title">Cause</h3>
{% include template-exception-cause.html %}

- You never provided any value to the DestinationTableName property (The default value = empty)
- You provided an empty string value has been provided to the DestinationTableName property

  </div>
  <div class="card-block">
     <h3 class="card-title">Fix</h3>
     
- ENSURE the destination table name exist. Make a SELECT * FROM [TheDestinationTable] in SSMS
- ENSURE the user have right. Log with the user information into SSMS and make the SELECT * FROM [TheDestinationTable]

  </div>
  
  <div class="card-block">
     <h3 class="card-title">BAD Example</h3>
     
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

  </div>
</div>
<br /><br />
