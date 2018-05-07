# SqlBulkCopy - WriteToServer requires an open and available Connection. The connection's current state is closed.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> WriteToServer requires an open and available Connection. The connection\'s current state is closed.

```csharp
using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    // Oops! The connection has never been opened
    // connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.BatchSize = 4000;
        bulkCopy.DestinationTableName = "TheDestinationTable";
        bulkCopy.WriteToServer(dt);
    }
}
```


```csharp
using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    // Oops! The connection has never been opened
    // connection.Open();

    foreach (DataTable dt in ds.Tables)
    {
        using (var bulkCopy = new SqlBulkCopy(connection))
        {

            bulkCopy.BatchSize = 4000;
            bulkCopy.DestinationTableName = "TheDestinationTable";
            bulkCopy.WriteToServer(dt);
        }
    }
}
```

## Solution

### Cause

- The connection is closed


### Fix

- ENSURE to open the connection
