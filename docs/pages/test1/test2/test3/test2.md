---
layout: default
title: My page ABC6
permalink: test4
---

z3

{% include section_start.md %}
Ooops! I did it againrrr7
{% include section_end.md %}

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
