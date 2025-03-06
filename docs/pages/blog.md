---
layout: cat2
permalink: /blog/
title: Blog
excerpt: Posts about my life and stuff.
---
{% for post in site.categories.blog %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})<br>
Tags: 
{% assign i = -1 %}
{% for tags in post.tags %}
{% assign i = i | plus:1 %}
{{ post.tags[i] | capitalize }};
{% else %}
N/a;
{% endfor %}
</p>
{{post.excerpt}} 
</div>
{% endfor %}