---
layout: post
title:  "Silent Witch Gaiden"
permalink: SilentWitchGaiden
categories: SilentWitchGaiden
exclude: true
translator: Seeker
editor: 
draft: true
noheader: true
comments: true
---

<h2>Silent Witch Gaiden Chapter List</h2>

*These events take place after the main story of "Silent Witch", so make sure you have read the entire main story before continuing. Keep in mind that some events may differ between the WN and LN.*

---

**Various Side Stories**

{% for post in site.categories.Gaiden0 reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

---

**Gaiden 1: Autumn of Rising Peas**

{% for post in site.categories.Gaiden1 reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

---

**Gaiden 2: Village of the Witches**

{% for post in site.categories.Gaiden2 reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}





