---
layout: cat2
permalink: /projects/
title: Projects
excerpt: Stuff I've made or am working on.
---
{% for post in site.categories.projects %}
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