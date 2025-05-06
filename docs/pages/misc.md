---
layout: cat1
permalink: /misc/
title: Misc
excerpt: For stuff that doesn't quite fit.
---
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.layout == "cat3" %}
<div class="PostBlock"> 
<p><a href="{{page.url}}">{{page.title}}</a>: {{page.excerpt}}</p> 
</div>
{% endif %}
{% endfor %}