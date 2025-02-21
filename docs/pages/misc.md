---
layout: page
permalink: /misc/
title: Misc
excerpt: For stuff that doesn't quite fit.
category: '1'
---
Dated Posts:
{% for post in site.categories.misc %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}
Non-Dated Pages:
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.categories contains "misc" %}
<div class="PostBlock"> 
<p><a href="{{page.url}}">{{page.title}}</a>: {{page.excerpt}}</p> 
</div>
{% endif %}
{% endfor %}