# SqlBulkCopy - WriteToServerAsync

## Description

The asynchronous version of WriteToServer. Copy all rows from the source to the destination table.

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    bulkCopy.DestinationTableName = "TheDestinationTable";
    
    // CALL WriteToServerAsync method.
    bulkCopy.WriteToServerAsync(dt, cancellationToken);
}
```