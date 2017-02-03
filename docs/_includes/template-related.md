test 7

{% assign isFirst = true %}
{% for num in (0..site.data.pages.size) %}	
	{% if site.data.pages[num].tags contains page.permalink %}
		{% if isFirst == true %}
			<h2>Troubleshooting</h2>
			<ul>
		{% endif %}
		<li><a href="{{ site.data.pages[num].url }}">{{ site.data.pages[num].url }}</a></li>
	{% endif %}
{% endfor %}
</ul>
