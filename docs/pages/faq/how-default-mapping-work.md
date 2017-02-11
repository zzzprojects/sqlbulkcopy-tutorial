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

{% highlight csharp %}
public class Order
{
    public int OrderId { get; set; }
    public int TransactionId { get; set; }
    public int CustomerId { get; set; }
    public string Reference { get; set; }
    public int Something { get; set; }
}
{% endhighlight %}


{% highlight csharp %}
internal void CreateDefaultMapping(int columnCount)
{
  for (int index = 0; index < columnCount; ++index)
    this.InnerList.Add((object) new SqlBulkCopyColumnMapping(index, index));
}
{% endhighlight %}

| Source | Destination |
| ------ | ----------- |
| TransactionId | OrderId |
| CustomerId    | Reference |
| Reference     | CustomerId |

Later the SqlBulkCopy will check...

The OrderId is an identity column in the database.

It will map to the next...

Final Mapping
| Source | Destination |
| ------ | ----------- |
| TransactionId | Something |
| CustomerId    | Reference |
| Reference     | CustomerId |

This can lead to multiple weird issue.
