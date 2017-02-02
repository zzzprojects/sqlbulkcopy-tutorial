---
layout: default
title: SqlBulkCopy - Troublshooting
permalink: troubleshooting
---

{% include template-h1.html %}

test1
<ul>
{% for num in (0..site.data.permalink.size) %}
	{% if site.data.permalink[num].category == page.permalink %}
	
	{{ site.data.permalink[num].permalink }}
		
	{% endif %}
{% endfor %}
</ul>
