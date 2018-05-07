# SqlBulkCopy - SqlRowCopied

## Description
Even raised after the number of row in the NotifyAfter has been processed.

## Example

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET SqlRowsCopied event.
    bulkCopy.SqlRowsCopied += (sender, args) => { /* code */ }; 
    
    bulkCopy.NotifyAfter = 4000;

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(reader);
}
```