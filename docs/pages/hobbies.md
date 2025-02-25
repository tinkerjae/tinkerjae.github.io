---
layout: cat2
permalink: /hobbies/
title: Hobbies
excerpt: Posts about hobbies I enjoy.
---
{% for post in site.categories.hobbies %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}