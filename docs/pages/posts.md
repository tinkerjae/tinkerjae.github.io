---
layout: page
permalink: /posts/
title: Posts
excerpt: This shows all of our posts ever made.
category: '1'
---
For posts sorted by category [click here](/categories/).
{% for post in site.posts %}
<div class='PostBlock'> <p><a href='{{post.url}}'>{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y' }})</p>
{{post.excerpt}} </div>
{% endfor %}
