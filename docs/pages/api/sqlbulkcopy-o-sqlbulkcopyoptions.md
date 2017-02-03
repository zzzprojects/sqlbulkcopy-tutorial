---
layout: default
title: SqlBulkCopy WriteToServerAsync
permalink: sqlbulkcopyoptions
---

{% include template-h1.html %}

## Description

Options

| Name | Default | Description |
| ---- | :-----: | ----------- |
| AllowEncryptedValueModifications | No | Allow for always encrypted |
| CheckConstraints | No |  Check constraints while data is being inserted. By default, constraints are not checked. |
| Default | Yes |  |
| FireTriggers | No |  When specified, cause the server to fire the insert triggers for the rows being inserted into the database. By default, triggers are not fired. |
| KeepIdentity | No | Preserve source identity values. When not specified, identity values are assigned by the destination. |
| KeepNulls | No | 	Preserve null values in the destination table regardless of the settings for default values. When not specified, null values are replaced by default values where applicable. |
| TableLock | No | Obtain a bulk update lock for the duration of the bulk copy operation. When not specified, row locks are used. |
| UseInternalTransaction | No | When specified, each batch of the bulk-copy operation will occur within a transaction. |

{% include template-example.html %} 
{% highlight csharp %}
using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    using (var bulkCopy = new SqlBulkCopy(connection, SqlBulkCopyOptions.CheckConstraints | SqlBulkCopyOptions.FireTriggers, null))
    {

        bulkCopy.BatchSize = 4000;
        bulkCopy.DestinationTableName = "TheDestinationTable";
        bulkCopy.WriteToServer(dt);
    }
}
{% endhighlight %}
