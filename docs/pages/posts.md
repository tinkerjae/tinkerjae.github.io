---
layout: page
permalink: /posts/
title: Posts
excerpt: This shows all of our posts ever made.
category: '1'
---
{% for post in site.posts %}
<div class='PostBlock'> <p><a href='{{post.url}}'>{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y' }})</p>
{{post.excerpt}} </div>
{% endfor %}
