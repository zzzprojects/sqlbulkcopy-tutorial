# SqlBulkCopy - The DestinationTableName property must be set before calling this method.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> The DestinationTableName property must be set before calling this method.

```csharp
using(var connection = new SqlConnection(FiddleHelper.GetConnectionStringSqlServer()))
{
    connection.Open();
    using (var sqlBulk = new SqlBulkCopy(connection))
    {
        // Oops! The destination name is Customer instead of Customers 		
        sqlBulk.DestinationTableName = "Customer";
        sqlBulk.WriteToServer(dt);
    }
}
```

[Try it](https://dotnetfiddle.net/Fmso3s)

## Solution

### Cause

- You never provided any value to the DestinationTableName property (empty by default).
- You provided an empty string to the DestinationTableName property.

### Fix

- ENSURE you provide value to the DestinationTableName property.
- ENSURE the value you provided is not empty.

```csharp
using(var connection = new SqlConnection(FiddleHelper.GetConnectionStringSqlServer()))
{
    connection.Open();
    using (var sqlBulk = new SqlBulkCopy(connection))
    {		
        sqlBulk.DestinationTableName = "Customer";
        sqlBulk.WriteToServer(dt);
    }
}
```

[Try it](https://dotnetfiddle.net/S7HL4P)