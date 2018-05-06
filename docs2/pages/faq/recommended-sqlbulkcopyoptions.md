---
layout: default
title: SqlBulkCopy - Recommended SqlBulkCopyOptions
permalink: recommended-sqlbulkcopyoptions
---

## Question

Which SqlBulkCopy options should we use by default?

## Answer

For common scenario:

- CheckConstraints
- FireTrigger

{% include template-example.html %} 
{% highlight csharp %}
var options = SqlBulkCopyOptions.CheckConstraints | SqlBulkCopyOptions.FireTriggers | SqlBulkCopyOptions.TableLock;
{% endhighlight %}

By default, all options are turned off which is very bad.

Even if your table doesn't yet have a constraint or trigger you need know what could happen in a year.

### Still not sure about which default option to use?

1. Talk to your team
2. Agreed on which default options to use within the company
3. Stick with it unless you have a special scenario
