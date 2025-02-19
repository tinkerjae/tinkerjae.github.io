---
layout: default
permalink: /posts/
title: Posts
---
{% for post in site.posts %}
<div>
<p><a href="{{post.url}}">{{post.title}}</a>({{post.date}})<br>
{{post.description}}</p>
</div>
{% endfor %}
^ This is a for loop for all posts.

{% for post in site.categories.project %}
<div>
<p><a href="{{post.url}}">{{post.title}}</a>({{post.date}})<br>
{{post.description}}</p>
</div>
{% endfor %}
^ This is a for loop, looking for posts with the category 'project'.