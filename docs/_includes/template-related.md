
<ul>
{% for num in (0..site.data.pages.size) %}	
	{% if site.data.pages[num].tags contains page.tags %}
		<li><a href="{{ site.data.pages[num].url }}">{{ site.data.pages[num].url }}</a></li>
	{% endif %}
{% endfor %}
</ul>
