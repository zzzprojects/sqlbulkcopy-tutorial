# SqlBulkCopy

## Description
SqlBulkCopy is the **FASTEST** way to insert multiples rows from a data source to a SQL Server/Azure.

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString, transaction))
{
    // SET BatchSize value.
    bulkCopy.BatchSize = 4000;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
```

## Options

| Name | Description |
| :--- | :---------- |
| SqlBulkCopyOptions | Bitwise flag to specifies one or more options. |

## Properties

| Name | Description |
| :--- | :---------- |
| BatchSize | Number of rows for a batch. |
| BulkCopyTimeout | Number of seconds maximum a batch can take before it times out. |
| ColumnMappings | Mapping between the source and destination columns. |
| DestinationTableName | Name of the destination table. |
| EnableStreaming | True to enable streaming for IDataReader object. |
| NotifyAfter | Number of rows to process before raising the SqlRowsCopied events. |

## Methods

| Name | Description |
| :--- | :---------- |
| WriteToServer | Copy all rows from the source to the destination table. |

## Events

| Name | Description |
| :--- | :---------- |
| SqlRowsCopied | Event raised after the number of row in the NotifyAfter has been processed. |