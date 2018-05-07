# SqlBulkCopy - WriteToServer

## Description
Copy all rows from the source to the destination table.

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    bulkCopy.DestinationTableName = "TheDestinationTable";
    
    // CALL WriteToServer method.
    bulkCopy.WriteToServer(dt);
}
```