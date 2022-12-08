---
layout: post
title:  "Honzuki Manga Part 4 SS List"
permalink: honzukimanga4
categories: HonzukiManga4
exclude: true
translator:
editor:
draft: true
noheader: true
comments: false
---

<h2>Honzuki Manga Part 4 SS List</h2>

{% for post in site.categories.HonzukiManga4 reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.title }}: {{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}
