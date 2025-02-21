---
layout: page
permalink: /categories/
title: Categories
excerpt: For posts sub divided into different categories.
---
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.category == "1" %}
<a href="{{ page.url }}">{{ page.title }}</a>: {{ page.excerpt }}
{% endif %}
{% endfor %}