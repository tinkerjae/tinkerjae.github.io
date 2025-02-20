---
layout: default
permalink: /misc/
title: Misc 
---
Stuff that doesn't quite fit.
{% for post in site.categories.misc %}
<div class="PostBlock"> 
<p><a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})</p> 
{{post.excerpt}} 
</div>
{% endfor %}