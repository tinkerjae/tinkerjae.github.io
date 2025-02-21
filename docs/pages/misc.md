---
layout: page
permalink: /misc/
title: Misc
description: For stuff that doesn't quite fit.
category: '1'
---
{{page.description}}<br>
Dated Pages:
<br>Nothing here yet, sorry!
{% for post in site.categories.misc %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}
Non-dated Pages:
{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.categories contains "misc" %}
<div class="PostBlock"> 
<p><a href="{{page.url}}">{{page.title}}</a>: {{page.excerpt}}</p> 
</div>
{% endif %}
{% endfor %}