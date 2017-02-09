---
layout: default
title: SqlBulkCopy - SqlBulkCopyOptions
permalink: sqlbulkcopyoptions
---

{% include template-h1.html %}

## Description
Bitwise flag that specifies one or more options.

{% include template-example.html %} 
{% highlight csharp %}
// SET SqlBulkCopyOptions value.
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString, SqlBulkCopyOptions.CheckConstraints | SqlBulkCopyOptions.FireTriggers))
{
	bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}

## Options

| Name | Default | Description |
| ---- | :-----: | ----------- |
| AllowEncryptedValueModifications | No | Allow for always encrypted |
| CheckConstraints | No |  Check constraints while data is being inserted. By default, constraints are not checked. |
| Default | Yes | Default options = None. |
| FireTriggers | No |  When specified, cause the server to fire the insert triggers for the rows being inserted into the database. By default, triggers are not fired. |
| KeepIdentity | No | Preserve source identity values. When not specified, identity values are assigned by the destination. |
| KeepNulls | No | 	Preserve null values in the destination table regardless of the settings for default values. When not specified, null values are replaced by default values where applicable. |
| TableLock | No | Obtain a bulk update lock for the duration of the bulk copy operation. When not specified, row locks are used. |
| UseInternalTransaction | No | When specified, each batch of the bulk-copy operation will occur within a transaction. |

## Remarks
You can specify more than one value by using the "|" operators (Logical OR).

{% include template-example.html %} 
{% highlight csharp %}
var options = SqlBulkCopyOptions.CheckConstraints | SqlBulkCopyOptions.FireTriggers | SqlBulkCopyOptions.TableLock;
{% endhighlight %}

## Recommendation
- SET CheckConstraints ON
- SET FireTriggers ON

### SET CheckConstraints ON
By default, SqlBulkCopy doesn't check constraint like default value.

Your table doesn't any constraint? It takes one second to be safe forever...

### SET FireTriggers ON
By default, SqlBulkCopy doesn't check trigger.

Your table doesn't any trigger? It takes one second to be safe forever...
