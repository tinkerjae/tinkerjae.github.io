---
layout: page
permalink: /categories/
title: Categories
description: For posts sub divided into different categories.
---
{{page.description}}
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.category == "1" %}
<a href="{{ page.url }}">{{ page.title }}</a>: {{ page.description }}
{% endif %}
{% endfor %}