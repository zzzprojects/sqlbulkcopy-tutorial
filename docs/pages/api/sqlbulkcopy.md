---
layout: default
title: SqlBulkCopy 
permalink: sqlbulkcopy
---

{% include template-h1.html %}
Fastest way to insert multiples rows from a data source to a SQL Server/Azure.

{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString, transaction))
{
    // SET BatchSize value.
    bulkCopy.BatchSize = 4000;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}

{% include begin-block-h2.html title='Options' %}
<table class="table table-striped table-hover table-responsive">
	<thead>
		<th>Name</th>
		<th>Description</th>		
	</thead>
	<tbody>
		<tr>
			<td><a href='batchsize'>SqlBulkCopyOptions</a></td>
			<td>Bitwise flag that specifies one or more options.</td>
		</tr>
	</tbody>
</table>
{% include end-block-h2.html %}

{% include begin-block-h2.html title='Properties' %}
<table class="table table-striped table-hover table-responsive">
	<thead>
		<th>Name</th>
		<th>Description</th>		
	</thead>
	<tbody>
		<tr>
			<td><a href='batchsize'>BatchSize</a></td>
			<td>Number of rows for a batch.</td>
		</tr>
		<tr>
			<td><a href='bulkcopytimeout'>BulkCopyTimeout</a></td>
			<td>Number of seconds maximum for a batch before it times out.</td>
		</tr>
		<tr>
			<td><a href='columnmappings'>ColumnMappings</a></td>
			<td>Mapping between the source and destination columns.</td>
		</tr>
		<tr>
			<td><a href='destinationtablename'>DestinationTableName</a></td>
			<td>Name of the destination table.</td>
		</tr>
		<tr>
			<td><a href='enablestreaming'>EnableStreaming</a></td>
			<td>True to enable streaming for IDataReader object.</td>
		</tr>
		<tr>
			<td><a href='notifyafter'>NotifyAfter</a></td>
			<td>Number of rows to process before raising the SqlRowsCopied events.</td>
		</tr>
	</tbody>
</table>
{% include end-block-h2.html %}

{% include begin-block-h2.html title='Methods' %}
<table class="table table-striped table-hover table-responsive">
	<thead>
		<th>Name</th>
		<th>Description</th>		
	</thead>
	<tbody>
		<tr>
			<td><a href='writetoserver'>WriteToServer</a></td>
			<td>Copy all rows from the source to the destination table.</td>
		</tr>
		<tr>
			<td><a href='writetoserverasync'>WriteToServerAsync</a></td>
			<td>The asynchronous version of WriteToServer. Copy all rows from the source to the destination table.</td>
		</tr>
	</tbody>
</table>
{% include end-block-h2.html %}

{% include begin-block-h2.html title='Events' %}
<table class="table table-striped table-hover table-responsive">
	<thead>
		<th>Name</th>
		<th>Description</th>		
	</thead>
	<tbody>
		<tr>
			<td><a href='sqlrowscopied'>SqlRowsCopied</a></td>
			<td>Even raised after the number of row in the NotifyAfter has been processed.</td>
		</tr>
	</tbody>
</table>
{% include end-block-h2.html %}
