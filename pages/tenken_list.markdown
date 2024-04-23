---
layout: page
title: TenKen
permalink: /Tenken/
---

<h2>TenKen Chapter List</h2>

<table>
{% for post in site.categories.TenKen reversed %}
  {% assign mod = post.chapter | modulo: 10 %}
  {% if mod == 0 or forloop.first %}
    <tr>
  {% endif %}
      <td><a href="{{ post.url }}">{{ post.chapter }}</a></td>
  {% if mod == 9 or forloop.last %}
    </tr>
  {% endif %}
{% endfor %}
</table>

<br>

[Expanded List](/Tenken/list)

<br>
