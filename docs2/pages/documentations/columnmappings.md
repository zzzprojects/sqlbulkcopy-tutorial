# SqlBulkCopy - ColumnMappings

## Description

Mapping between the source and destination columns.

```csharp
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // SET ColumnMappings values.
    bulkCopy.ColumnMappings.Add("TheColumnInt", "TheColumnInt");
    bulkCopy.ColumnMappings.Add("TheColumnString", "TheColumnString");

    bulkCopy.DestinationTableName = "TheDestinationTable";
    bulkCopy.WriteToServer(dt);
}
```

## Recommendation
- Always map column explicitly

### Always map column explicitly
The default mapping under the hood of SqlBulkCopy may cause some weird issue because column are not mapped by name but by ordinal. When your table containt an identity value, you may end up by value mapped to wrong column!

See: [SqlBulkCopy giving FOREIGN KEY constraint error](http://stackoverflow.com/a/39728073/5619143)