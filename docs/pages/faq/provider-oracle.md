---
layout: default
title: SqlBulkCopy - Oracle
permalink: oracle
---

{% include template-h1.html %}

## Problem

You found out SqlBulkCopy is not supported for Oracle.

But you still want to know what's the **fastest way to insert** in Oracle using theses providers:

- Oracle.DataAccess
- Oracle.ManagedDataAccess
- [Devart.Data.Oracle](https://www.devart.com/dotconnect/oracle/){:target="_blank"}

## Solution
You can use one of the following solution

- [OracleBulkCopy](solution-oraclebulkcopy) _(Not recommended)_
- [OracleLoader](solution-oracleloader) _(Not recommended)_
- [Array Bindings](solution-array-bindings)
- [.NET Bulk Operations](solution-net-bulk-operations)


## Solution - OracleBulkCopy
Documentation: https://docs.oracle.com/cd/E17666_01/doc/win.112/e17357/OracleBulkCopyClass.htm

This solution only support the provider Oracle.DataAccess.

Due to the limitation, unflexibility, and by experience! We highly recommand you to use the **Array Bindings solution** over OracleBulkCopy.

Limitation:

- DO NOT support Oracle.ManagedDataAccess
- DO NOT support all column types
- DO NOT check constraints
- DO NOT check triggers
- CANNOT perform INSERT RETURNING statement

> Once you start using Array Bindings, you never look back at this solution.

## Solution - OracleLoader
Documentation: http://www.devart.com/dotconnect/oracle/docs/?Devart.Data.Oracle~Devart.Data.Oracle.OracleLoader.html

This solution only support the provider Devart.Data.Oracle.

Under the hood, the OracleLoader use the OracleBulkCopy. So for the same limitation reason, we recommend using Array Binding over this solution.

## Solution - Array Bindings

## Solution - .NET Bulk Operations with Oracle

The .NET Bulk Operations use under the hood the Array Bindings solution and support all Oracle provider:

- Oracle.DataAccess
- Oracle.ManagedDataAccess
- Devart.Data.Oracle


and all kind of bulk operations:
- BulkInsert
- BulkUpdate
- BulkDelete
- BulkMerge

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



{:target="_blank"}
SqlBulkCopy is not available for Oracle. However, you can use one of these class:



Nothing is available for Oracle.ManagedDataAccess....

But before using it, wait!!!

WE DON'T RECOMMAND USING OracleBulkCopy && OracleLoader

Both of these class are limited

Limitation: https://docs.oracle.com/cd/E51173_01/win.122/e17732/featBulkCopy.htm#ODPNT213

So what else?

We recommand using instead Array insert.

{% include begin-block-h2.html title='Alternative Solution' %}

