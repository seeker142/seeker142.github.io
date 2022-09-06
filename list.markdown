---
layout: page
title: Chapter List
permalink: /Tenken/
---

<p>
{% for post in site.posts reversed %}
  {% assign mod = post.chapter | modulo: 10 %}
  {% if mod == 0 %}
    <br>
  {% endif %}
  <a href="{{ post.url }}">{{ post.chapter }}</a>
{% endfor %}
</p>
