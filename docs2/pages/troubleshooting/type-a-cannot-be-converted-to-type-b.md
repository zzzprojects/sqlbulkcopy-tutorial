# SqlBulkCopy - The given value of type String from the data source cannot be converted to type int of the specified target column.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> The given value of type String from the data source cannot be converted to type int of the specified target column.

```csharp
var dt = new DataTable();
dt.Columns.Add("TheColumnInt");
dt.Columns.Add("TheColumnString");

for (int i = 0; i < 100; i++)
{
    // Oops! The value added for "TheColumnInt" is empty
    dt.Rows.Add("", i);
}

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
        bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

        bulkCopy.BatchSize = 4000;
        bulkCopy.DestinationTableName = "TheDestinationTable";
        bulkCopy.WriteToServer(dt);
    }
}
```

## Solution

### Cause

- You provided an empty value which cannot be converted to another type.

### Fix

- ENSURE provided value is valid for the destination type.
- CREATE column by specifying the type to get the error before executing WriteToServer method.

### Example
```csharp
var dt = new DataTable();
dt.Columns.Add("TheColumnInt", typeof(int));
dt.Columns.Add("TheColumnString", typeof(string));
```
