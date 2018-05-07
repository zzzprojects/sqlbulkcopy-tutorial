# SqlBulkCopy - Cannot access destination table '[TheInvalidTableName]'.

## Problem

You execute the method WriteToServer, and the following error is thrown:

> Cannot access destination table '[TheInvalidTableName]'.

```csharp
// Oops! The table name is invalid
string destinationName = "[TheInvalidTableName]";

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

- You provided an invalid schema name.
- You provided an invalid table name.
- The user doesn't have the right to the schema name.
- The user doesn't have the right to the table name.

### Fix

- ENSURE the schema name is valid.
- ENSURE the table name is valid.

If the schema and table name was already valid:

- LOG into SSMS with the user/password used by the application and perform a SELECT statement to ensure he has access to it.
