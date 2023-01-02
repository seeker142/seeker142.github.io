---
layout: post
title:  "Honzuki SS List"
permalink: honzuki
categories: HonzukiSS
exclude: true
translator: Seeker (+DeepL)
editor: 
draft: true
noheader: true
comments: true
---

<h2>Honzuki Part 5 SS List</h2>

{% for post in site.categories.HonzukiSS reversed %}
{% unless post.url == page.url %}
  <a href="{{ post.url }}">{{ post.title }}: {{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

<h2>Honzuki Manga Part 3 SS List</h2>

{% for post in site.categories.HonzukiManga3 reversed %}
{% unless forloop.first %}
  <a href="{{ post.url }}">{{ post.title }}: {{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

<h2>Honzuki Manga Part 4 SS List</h2>

{% for post in site.categories.HonzukiManga4 reversed %}
{% unless forloop.first %}
  <a href="{{ post.url }}">{{ post.title }}: {{ post.excerpt | remove: '<h2>' | remove: '</h2>' }}
{% endunless %}
{% endfor %}

---

Click this if you are allergic to honorifics: <button onclick="localizeToggle()">Localize Toggle</button>

<div id="result"></div>
<script>
if (typeof(Storage) === "undefined") {
  document.getElementById("result").innerHTML = "Sorry, your browser does not support web storage.";
}
</script>

<script>
function localizeToggle()
{
  if (localStorage.getItem("localize") &&
  	localStorage.getItem("localize") === "true")
  {
    localStorage.setItem("localize", "false")
	document.getElementById("result").innerHTML = "Localization OFF";
  }
  else
  {
    localStorage.setItem("localize", "true")
	document.getElementById("result").innerHTML = "Localization ON";
  }
  
  localize();
}
</script>


