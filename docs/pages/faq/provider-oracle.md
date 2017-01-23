---
layout: default
title: SqlBulkCopy - Oracle
permalink: oracle
---

{% include template-h1.html %}

{% include begin-block-h2.html title='Problem' %}

Unfortunately, SqlBulkCopy doesn't support Oracle.

But you still want to know what's the **fastest way to insert** using:

- Oracle.DataAccess
- Oracle.ManagedDataAccess
- [Devart.Data.Oracle](https://www.devart.com/dotconnect/oracle/){:target="_blank"}

{% include begin-block-h2.html title='Solution' %}
SqlBulkCopy is not available for Oracle. However, you can use one of these class:

- [OracleBulkCopy](https://docs.oracle.com/cd/E17666_01/doc/win.112/e17357/OracleBulkCopyClass.htm) for Oracle.DataAccess
- [OracleLoader](http://www.devart.com/dotconnect/oracle/docs/?Devart.Data.Oracle~Devart.Data.Oracle.OracleLoader.html) for Devart.Data.Oracle

Nothing is available for Oracle.ManagedDataAccess....

But before using it, wait!!!

WE DON'T RECOMMAND USING OracleBulkCopy && OracleLoader

Both of these class are limited

Limitation: https://docs.oracle.com/cd/E51173_01/win.122/e17732/featBulkCopy.htm#ODPNT213

So what else?

We recommand using instead Array insert.

{% include begin-block-h2.html title='Alternative Solution' %}
One alternative solution is using [.NET Bulk Operations](http://bulk-operations.net/) which support all oracle provider:

- Oracle.DataAccess
- Oracle.ManagedDataAccess
- Devart.Data.Oracle

and all kind of bulk operations:
- BulkInsert
- BulkUpdate
- BulkDelete
- BulkMerge

{% include begin-code.html %}
{% highlight csharp %}

// Easy to use
var bulk = new BulkOperation(connection);
bulk.BulkInsert(dt);
bulk.BulkUpdate(dt);
bulk.BulkDelete(dt);
bulk.BulkMerge(dt);

// Easy to customize
var bulk = new BulkOperation<Customer>(connection);
bulk.BatchSize = 1000;
bulk.ColumnInputExpression = c => new { c.Name,  c.FirstName };
bulk.ColumnOutputExpression = c => c.CustomerID;
bulk.ColumnPrimaryKeyExpression = c => c.Code;
bulk.BulkMerge(customers);

{% endhighlight %}
{% include end-code.html %}
