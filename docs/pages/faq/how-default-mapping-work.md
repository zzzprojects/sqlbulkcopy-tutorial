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

Let use the following class
{% highlight csharp %}
public class Order
{
    public int OrderId { get; set; }
    public int TransactionId { get; set; }
    public int CustomerId { get; set; }
    public DateTime DateCreated { get; set; }
    public int InvoiceId { get; set; }
}
{% endhighlight %}

The problem is SqlBulkCopy auto map column by ordinal:

{% highlight csharp %}
internal void CreateDefaultMapping(int columnCount)
{
  for (int index = 0; index < columnCount; ++index)
    this.InnerList.Add((object) new SqlBulkCopyColumnMapping(index, index));
}
{% endhighlight %}

So if your first column in the table is an identity value, here is the mapping by ordinal that will be created:

| Source        | Destination   |
| ------------- | ------------- |
| TransactionId | OrderId       |
| CustomerId    | TransactionId |
| Reference     | CustomerId    |

Fortunately, later in the code, SqlBulkCopy is enough smart to find out the OrderId is an identity value so he will make the column TransactionId from the source to the next available column matching the type.

First, he will try to map the TransactionId to the DateCreated column in the source, but since the type doesn't match, he will move to the next destination column.

He will now find a perfect match between TransactionId from the source and InvoiceId from the Destination.

The Final Mapping:

| Source        | Destination |
| ------------- | ----------- |
| TransactionId | InvoiceId   |
| CustomerId    | Reference   |
| Reference     | CustomerId  |

## StackOverflow Reference
- [SqlBulkCopy giving FOREIGN KEY constraint error](http://stackoverflow.com/questions/39684342/sqlbulkcopy-giving-foreign-key-constraint-error/)
