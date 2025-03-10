---
layout: page
title: Chapter List
permalink: /Tenken/list
---

{% for post in site.categories.TenKen reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}
