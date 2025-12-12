---
layout: default
title: Posts
permalink: /posts/
tags:
    - test 1
    - test 2 
    - test 3
---
This page shows all of my posts !!
{% for post in site.posts %}
<p>
<a href="{{ post.url }}">{{ post.title }}</a> ({{post.date}})<br>
{% if post.tags.size > 1 %}
Tags: 
    {% for tag in post.tags %}
        <a href="/all/{{ tag | downcase }}">{{ tag }}</a>; 
    {% endfor %}
{% endif %}
</p>
{% endfor %}