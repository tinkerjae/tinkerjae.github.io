---
layout: cat2
permalink: /hobbies/
title: Hobbies
excerpt: Posts about hobbies I enjoy.
---
<br>
{% for post in site.categories.hobbies %}
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
    {{post.excerpt | strip_html}}<br>
    <br>
</p>
</div>
{% endfor %}