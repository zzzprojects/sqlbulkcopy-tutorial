# SqlBulkCopy - EnableStreaming

## Description
True to enable streaming for IDataReader object.

- Type: System.Boolean
- Default Value: false

## Example

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET EnableStreaming value.
    bulkCopy.EnableStreaming = true;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(reader);
}
```