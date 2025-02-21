---
layout: page
permalink: /blog/
title: Blog
excerpt: Posts about my life and stuff.
category: '1'
---
{% for post in site.categories.blog %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}