---
layout: default
permalink: /
title: Welcome!
excerpt: The landing/home page for my website.
---
Hi! Welcome to my new site! This website is currently a work in progress. 
This website exists as my personal home on the internet where I can post about my [daily life](/blog/), [projects](/projects/), [hobbies](/hobbies/), poetry, and cool stuff I've found on the internet. 

If you'd like to make a website like this, check out my [web dev resources](/webdevresources/).
<hr>
<h1><u>Sitemap</u></h1>
[Home](/): {{page.excerpt}}

[Categories](/categories/): My posts divided into different categories.

{% assign sortedPages = site.pages | sort: 'title' %}
{% for page in sortedPages %}   
{% if page.layout == "cat2" %}
[{{page.title}}]({{page.url}}): {{page.excerpt}}
{% endif %}
{% endfor %}

[Misc](/misc/): For stuff that doesn't quite fit anywhere else.

<hr>
<h1><u>Contact Me</u></h1>
If you wanna hit me up, here's my main methods of contact.

Email (remove NOSPAM from the address): <a href="mailto:{{site.email}}">{{site.email}}</a>

<hr>
<h1><u>Webring</u></h1>
I'm apart of the Maker Webring!
<div id='D1D1D0904CC346DB' class="MakerWebring">
    <script type="text/javascript" src="https://github.com/tinkerjae/tinkerjae.github.io/blob/main/docs/assets/webring/onionring-variables.js"></script>
    <script type="text/javascript" src="https://github.com/tinkerjae/tinkerjae.github.io/blob/main/docs/assets/webring/onionring-widget.js"></script>
</div>