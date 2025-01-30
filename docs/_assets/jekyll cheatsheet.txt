Proudly stolen from https://devhints.io/jekyll
Some things have been changed, but not much.

Jekyll cheatsheet
Installation

# Install the gems
gem install jekyll bundler

# Create a new site at `./myblog`
jekyll new myblog
cd myblog

# Optional: if you're targeting github-pages,
# use this Gemfile instead.
cat > Gemfile <<-END
source 'https://rubygems.org'
gem 'github-pages', group: :jekyll_plugins
END

bundle exec jekyll serve

See: Jekyll quickstart
See: github/pages-gem
Directories

./
├── _config.yml
├── _data
│   └── members.yml
├── _drafts
│   ├── begin-with-the-crazy-ideas.md
│   └── on-simplicity-in-technology.md
├── _includes
│   ├── footer.html
│   └── header.html
├── _layouts
│   ├── default.html
│   └── post.html
├── _posts
│   ├── 2007-10-29-why-every-programmer-should-play-nethack.md
│   └── 2009-04-26-barcamp-boston-4-roundup.md
├── _sass
│   ├── _base.scss
│   └── _layout.scss
├── _site
├── .jekyll-cache
│   └── Jekyll
│       └── Cache
│           └── [...]
├── .jekyll-metadata
└── index.html # can also be an 'index.md' with valid front matter

Front-matter#
Basic frontmatter

---
layout: post
title: Hello
---
Hello! this is my post.

Attach metadata to a page by adding them on top of the page, delimited by ---. See: Front-matter
Other frontmatter stuff

permalink: '/hello'
published: false
category: apple
categories: ['html', 'css']
tags: ['html', 'css']

Configuration

In _config.yml:

source: .
destination: _site
exclude:
- Gemfile
- Gemfile.lock
include: ['.htaccess']

All config keys are optional. See: Configuration
Markup#
Page variables

<title>
  {{ page.title }}
</title>

Filters

<p>
  {{ page.description | truncate_words: 20 }}
</p>

Loops

{% for post in site.posts %}
  <a href="{{ post.url }}">
    <h2>{{ post.title }}</h2>
    <p>{{ post.date | date_to_string }}</p>
  </a>
{% endfor %}

Dates

{{ page.date | date: "%b %d, %Y" }}

Conditionals

{% if page.image.feature %}
  ...
{% elsif xyz %}
  ...
{% else %}
  ...
{% endif %}

{% if page.category == 'React' %}
{% if page.category == 'React' or page.featured %}
{% if page.tags contains 'Featured' %}

Case

{% case shipping.title %}
  {% when 'international' %}
     Arriving in 2-3 weeks
  {% when 'Domestic' %}
     Arriving in 2-3 days
  {% else %}
     Thank you for your order!
{% endcase %}

Includes (partials)

{% include header.html %}

<!-- Including local vars -->
{% include header.html page=page %}

Comments

{% comment %}
  This is a comment!
{% endcomment %}

Variables#
Top-level variables
{{ site }} 	Data from config.yml
{{ page }} 	From frontmatter, and page-specific info
{{ content }} 	HTML content (use in layouts)
{{ paginator }} 	Paginator

See: Variables
Site

{{ site.time }}

site.time 	Current time
site.pages 	List of pages
site.posts 	List of blog posts
site.related_posts 	List of posts related to current
site.categories.CATEGORY 	List
site.tags.TAG 	List
site.static_files 	List
Page

{{ page.content }}  - un-rendered content
{{ page.title }}
{{ page.excerpt }}  - un-rendered excerpt
{{ page.url }}
{{ page.date }}
{{ page.id }}       - unique id for RSS feeds
{{ page.categories }}
{{ page.tags }}
{{ page.path }}
{{ page.dir }}
{{ page.excerpt | remove: '<p>' | remove: '</p>' }}
{{ page.excerpt | strip_html }}

<!-- blog pagination: -->
{{ page.next }}
{{ page.previous }}

Filters#
Dates

{{ site.time | date: "%Y %m %d" }}

date_to_xmlschema 	→ 2008-11-07T13:07:54-08:00
date_to_rfc822 	→ Mon, 07 Nov 2008 13:07:54 -0800
date_to_string 	→ 07 Nov 2008
date_to_long_string 	→ 07 November 2008
date: ‘%Y %m %d’ 	→ 2017 Nov 7
Preprocessors

{{ page.description | markdownify }}

textilize 	Textile
markdownify 	Markdown
jsonify 	JSON
sassify 	Sass
scssify 	SCSS
smartify 	Smartypants
Array filters

{{ site.pages | where: "year", "2014" }}

where: “year”, “2014” 	 
where_exp: “item”, “item.year >= 2014” 	 
group_by: “genre” 	→ {name, items}
group_by_exp: “item”, “item.genre” 	→ {name, items}
sort 	 
sort: ‘author’ 	 
uniq 	 
first 	 
last 	 
join: ’,’ 	 
array_to_sentence_string 	→ "X, Y and Z"
map: ‘post’ 	Works like ‘pluck’
size 	 
push: ‘xxx’ 	Adds an item
String filters

{{ page.title | default: "xxx" }}

default: ‘xxx’ 	 
upcase 	 
downcase 	 
remove: ‘p’ 	 
replace: ‘super’, ‘mega’ 	 
remove_first: ‘p’ 	 
replace_first: ‘super’, ‘mega’ 	 
truncate: 5 	 
truncatewords: 20 	 
prepend: ‘Mr. ‘ 	 
append: ‘Jr.’ 	 
camelize 	 
capitalize 	 
strip_html 	 
strip_newlines 	 
newlines_to_br 	 
split: ’,’ 	 
escape 	 
escape_once 	 
slice: -3, 3 	 

See: String filters
String filters (Jekyll-only)

{{ page.excerpt | number_of_words }}

number_of_words 	 
slugify 	 
xml_escape 	→ CDATA
cgi_escape 	→ foo%2Cbar
uri_escape 	→ foo,%20bar
Numbers

{{ site.posts.size | minus: 2 }}

minus: 2 	 
plus: 2 	 
times: 2 	 
divided_by: 2 	 
modulo: 2 	 
ceil 	 
floor 	 
round 	 
Paginator#
Paginator setup

Add this to _config.yml:

paginate: 5
paginate_path: "blog/:num"

See: Paginator
Numbers

{{ paginator.page }}         - page number
{{ paginator.total_posts }}
{{ paginator.total_pages }}
{{ paginator.per_page }}

Iterating through posts

{% for post in paginator.posts %} ... {% endfor %}

Previous button

{% if paginator.total_pages > 1 %}
  {% if paginator.previous_page %}
    <a href="{{ paginator.previous_page_path }}">Previous</a>
  {% else %}
  {% endif %}
{% endif %}

{{ paginator.next_page }}     - page number
{{ paginator.next_page_path }}

Blogging#
Paths

_posts/YEAR-MONTH-DAY-title.md

See: Blogging
Image paths

![My helpful screenshot]({{ site.url }}/assets/screenshot.jpg)

See: Image paths
Drafts

vi _drafts/a-draft-post.md
jekyll build --drafts

Posts in _drafts only show up in development, but not production. See: Drafts
Defining excerpts

---
title: My blog post
excerpt: This post is about cats
---

Hello, let's talk about cats. (···)

Put a key excerpt in the frontmatter. See: Excerpts
Displaying excerpts

{{ post.excerpt }}

{{ post.excerpt | remove: '<p>' | remove: '</p>' }}
{{ post.excerpt | strip_html }}

Excerpt separator

---
excerpt_separator: <!--more-->
---

Excerpt here
<!--more-->
More post body here

Alternatively, you can put excerpts inline in your post by defining excerpt_separator.
Permalinks

# _config.yml
permalink: date   # /:categories/:year/:month/:day/:title.html
permalink: pretty # /:categories/:year/:month/:day/:title/
permalink: none   # /:categories/:title.html
permalink: "/:title"

See: Permalinks
More features#
Data

_data/members.yml

{% for member in site.data.members %}
  ...
{% endfor %}

See: Data
Collections

# _config.yml
collections:
  - authors

# _/authors/a-n-roquelaire.md
---
name: A. N. Roquelaire
real_name: Anne Rice
---

{% for author in site.authors %}

See: Collections
Code highlighter

{% highlight ruby linenos %}
def show
  ...
end
{% endhighlight %}

Integration#
Bundler

In _plugins/bundler.rb:

require "bunder/setup"
Bundler.require :default

Compass

    Compass
    Asset pipeline

