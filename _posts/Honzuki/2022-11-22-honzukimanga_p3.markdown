---
layout: post
title:  "Honzuki Manga Part 3 SS List"
permalink: honzukimanga3
categories: HonzukiManga3
exclude: true
translator:
editor:
draft: true
noheader: true
comments: false
---

<h2>Honzuki Manga Part 3 SS List</h2>

{% for post in site.categories.HonzukiManga3 reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.title }}: {{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}
