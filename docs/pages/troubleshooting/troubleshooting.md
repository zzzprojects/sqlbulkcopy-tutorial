---
layout: default
title: SqlBulkCopy - Troublshooting
permalink: troubleshooting
---

{% include template-h1.html %}

<ul>
{% for num in (0..site.data.permalink.size) %}	
	{% if site.data.permalink[num].category == page.permalink %}
		<li><a href="{{ site.data.permalink[num].permalink }}">{{ site.data.permalink[num].permalink }}</a></li>
	{% endif %}
{% endfor %}
</ul>
