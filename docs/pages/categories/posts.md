---
layout: cat2
permalink: /posts/
title: Posts
excerpt: This shows all of our posts ever made.
---
{% for post in site.posts %}
<div class="PostBlock"> 
<p>
    <a href="{{post.url}}">{{post.title}}</a>    ({{ post.date | date: '%B %-d, %Y'}})<br>
    Tags: 
        {% assign i = -1 %}
        {% for tags in post.tags %}
        {% assign i = i | plus:1 %}
        {{ post.tags[i] | capitalize }};
        {% else %}
        n/a;
        {% endfor %}<br>
    {{post.excerpt | strip_html}}
</p>
</div>
{% endfor %}
