# SqlBulkCopy - DestinationTableName

## Description
Name of the destination table.

- Type: System.Int32
- Default Value: String.Empty

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET DestinationTableName value.
    bulkCopy.DestinationTableName = "TheDestinationTable";

    // ...ColumnMappings & Options...
    bulkCopy.WriteToServer(dt);
}
```