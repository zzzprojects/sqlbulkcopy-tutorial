# SqlBulkCopy - Value cannot be null.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> Value cannot be null.'

```csharp
// Oops! The destination name is null
string destinationName = null;

using (var connection = new SqlConnection(My.Config.ConnectionStrings.BulkOperations))
{
    connection.Open();

    using (var bulkCopy = new SqlBulkCopy(connection))
    {
        bulkCopy.DestinationTableName = destinationName;
        bulkCopy.WriteToServer(dt);
    }
}
```

## Solution

### Cause

- You provided a null value to the DestinationTableName property.

### Fix

- ENSURE the value you provided is not null.
