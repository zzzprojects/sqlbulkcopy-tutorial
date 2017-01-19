---
layout: default
title: My page ABC6
permalink: test4
---

Ooops! I did it againrrr

{% highlight csharp %}
var audit = new Audit();
audit.CreatedBy = "ZZZ Projects"; // Optional
ctx.SaveChanges(audit);

// Access to all auditing information
var entries = audit.Entries;
foreach(var entry in entries)
{
    foreach(var property in entry.Properties)
    {
    }
}
{% endhighlight %}
