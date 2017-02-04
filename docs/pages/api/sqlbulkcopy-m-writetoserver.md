---
layout: default
title: SqlBulkCopy WriteToServer
permalink: writetoserver
---

{% include template-h1.html %}

## Description
Copy all rows from the source to the destination table.

## Example
{% include template-example.html %} 
{% highlight csharp %}
using (SqlBulkCopy bulkCopy = new SqlBulkCopy(connectionString))
{
    // ...ColumnMappings & Options...
    
    // CALL WriteToServer method.
    bulkCopy.WriteToServer(dt);
}
{% endhighlight %}
