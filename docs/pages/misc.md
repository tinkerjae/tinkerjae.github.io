---
layout: default
title: Misc
permalink: /misc/
excerpt: What do you think this is? 
categories:
    - misc
---
All the miscelleaneous stuff with nowhere else to go on my site.
{% for page in site.pages %}
{% if page.categories contains "Misc" or page.categories contains "misc" %}
<p><a href="{{ page.url }}">{{ page.title }}</a>: {{ page.content | strip_html | truncatewords: 7  }}</p>
{% endif %}
{% endfor %} 