---
layout: cat1
permalink: /categories/
title: Categories
excerpt: For posts/pages sub divided into different categories.
---
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.layout == "cat2" %}
[{{page.title}}]({{page.url}}): {{page.excerpt}}
{% endif %}
{% endfor %}