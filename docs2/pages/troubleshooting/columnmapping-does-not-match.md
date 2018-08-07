# SqlBulkCopy - The given ColumnMapping does not match up with any column in the source or destination.

## Problem

You execute the method WriteToServer, and the following error is thrown:

The given ColumnMapping does not match up with any column in the source or destination.

```csharp
using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        // Oops! The destination column is case sensitive, it should be instead "TheColumnInt"
        bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnint");
        bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

        bulkCopy.BatchSize = 4000;
        bulkCopy.DestinationTableName = "TheDestinationTable";
        bulkCopy.WriteToServer(dt);
    }
}
```

## Solution

### Cause

- You didn't provide any ColumnMappings, and there is more column in the source than in the destination.
- You provided an invalid column name for the source.
- You provided an invalid column name for the destination.

### Fix

- ENSURE to provide a ColumnMappings
- ENSURE all values for source column name are valid and case sensitive.
- ENSURE all values for destination column name are valid and case sensitive.
- MAKE the source case insensitive

> You cannot make the destination column name case insensitive.

### Example - MAKE the source case insensitive

```csharp
var dt = new DataTable();
dt.CaseSensitive = false;
dt.Columns.Add("TheColumnInt", typeof(int));
dt.Columns.Add("TheColumnString");
```


