test 1

{% assign hasOne = false %}
{% for num in (0..site.data.pages.size) %}	
	{% if site.data.pages[num].tags contains page.permalink %}
		{% assign hasOne = true %}
	{% endif %}
{% endfor %}

{% if hasOne == true %}
## Troubleshooting
<ul>
{% for num in (0..site.data.pages.size) %}	
	{% if site.data.pages[num].tags contains page.permalink %}
		<li><a href="{{ site.data.pages[num].url }}">{{ site.data.pages[num].url }}</a></li>
	{% endif %}
{% endfor %}
</ul>
{% endif%}
