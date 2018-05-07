# SqlBulkCopy - The DestinationTableName property must be set before calling this method.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> The DestinationTableName property must be set before calling this method.'

```csharp
// Oops! The destination name is empty
string destinationName = "";

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

- You never provided any value to the DestinationTableName property (empty by default).
- You provided an empty string to the DestinationTableName property.

### Fix

- ENSURE you provide value to the DestinationTableName property.
- ENSURE the value you provided is not empty.