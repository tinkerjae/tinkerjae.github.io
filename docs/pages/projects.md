---
layout: page
permalink: /projects/
title: Projects
excerpt: Stuff I've made or am working on.
category: '1'
---
{% for post in site.categories.projects %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}