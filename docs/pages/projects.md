---
layout: cat2
permalink: /projects/
title: Projects
excerpt: Stuff I've made or am working on.
---
{% for post in site.categories.projects %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}