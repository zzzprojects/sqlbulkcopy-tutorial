---
layout: default
title: SqlBulkCopy - How the default mapping work
permalink: how-default-mapping-work
---

{% include template-h1.html %}

## Description
Hey SqlBulkCopy can map column automaticality, it's not is great?

At first sight yes, but once you understand how it works, you will always map all your columns explicitly!

## Under the hood

### Unit of Test
Let use,

The following DataTable to map
{% highlight csharp %}
var dt = new DataTable();
dt.Columns.Add("SourceOrderId", typeof(int));
dt.Columns.Add("SourceTransactionId", typeof(int));
dt.Columns.Add("SourceCustomerId", typeof(int));
{% endhighlight %}

to the following SQL table:
{% highlight sql %}
CREATE TABLE DestinationOrder
(
    DestinationOrderId INT IDENTITY(1, 1),
    DestinationTransactionId INT,
    DestinationCustomerId INT,
    DestinationDateCreated DATETIME2,
    DestinationInvoiceId INT
)
{% endhighlight %}

### Problem

Let say we want to insert only the following column:
- SourceOrderId
- SourceTransactionId
- SourceCustomerId

#### Step 1
The first step of the default mapping is simply performing an auto-mapping by ordinal:

{% highlight csharp %}
internal void CreateDefaultMapping(int columnCount)
{
  for (int index = 0; index < columnCount; ++index)
    this.InnerList.Add((object) new SqlBulkCopyColumnMapping(index, index));
}
{% endhighlight %}

| Source              | Destination              |
| ------------------- | ------------------------ |
| SourceTransactionId | DestinationOrderId       |
| SourceCustomerId    | DestinationTransactionId |
| SourceReference     | DestinationCustomerId    |

As you already see, problem is comming. They are already not mapping to the right column!

#### Step 2
The second step will check destination column type and identity column.

The default mapping will discover the DestinationOrderId is an identity column and should not be mapped unless you have the option KeepIdentity turned on.

The default mapping will try to map the SourceTransactionId to the next column available.

- It will try to map to SourceDateCreated but the type doesn't match
- It will try to map to SourceInvoiceId and will find a perfect match!

The mapping is now:

| Source              | Destination            |
| ------------------- | ---------------------- |
| SourceTransactionId | DestinationInvoiceId   |
| SourceCustomerId    | DestinationReference   |
| SourceReference     | DestinationCustomerId  |

Without a doubt, this mapping will lead to many error. Wrong source property are mapping to wrong destination column!

## StackOverflow Reference
- [SqlBulkCopy giving FOREIGN KEY constraint error](http://stackoverflow.com/questions/39684342/sqlbulkcopy-giving-foreign-key-constraint-error/)
