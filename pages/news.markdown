---
layout: page
title: News
permalink: /News/
navigation_menu: true
---

{% for post in site.categories.News reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

