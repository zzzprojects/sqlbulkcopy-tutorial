test 6

<ul>
{% assign isFirst = true %}
{% for num in (0..site.data.pages.size) %}	
	{% if site.data.pages[num].tags contains page.permalink %}
		{% if isFirst == true %}
			<h2>Troubleshooting</h2>
		{% endif %}
		<li><a href="{{ site.data.pages[num].url }}">{{ site.data.pages[num].url }}</a></li>
	{% endif %}
{% endfor %}
</ul>
