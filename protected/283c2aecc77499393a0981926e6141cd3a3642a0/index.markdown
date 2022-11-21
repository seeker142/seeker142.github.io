---
layout: page
title: Protected
exclude: true
---

Click to enable access to password protected pages: <button onclick="accessToggle()">Access Toggle</button>

<div id="result"></div>
<script>
if (typeof(Storage) === "undefined") {
  document.getElementById("result").innerHTML = "Sorry, your browser does not support web storage.";
}
</script>

<div class="status">
<p>Current Status: Restricted</p>
</div>


Drafts:

<p>
{% for post in site.categories.TenKenDraft reversed %}
  {% assign mod = post.chapter | modulo: 10 %}
  {% if mod == 0 %}
    <br>
  {% endif %}
  <a href="{{ post.url }}">{{ post.chapter }}</a>
{% endfor %}
</p>


<script>	
function printAccess() {
  console.log(localStorage.getItem("access"));
  var element = document.getElementsByClassName("status")[0];
  if (localStorage.getItem("access") === "1") {
    element.innerHTML = element.innerHTML.replace(/Restricted\b/g, 'Allowed');
  }
  else {
    element.innerHTML = element.innerHTML.replace(/Allowed\b/g, 'Restricted');
  }
}

printAccess();

function accessToggle()
{
  if (localStorage.getItem("access") &&
  	localStorage.getItem("access") === "1")
  {
    localStorage.setItem("access", "0")
  }
  else
  {
    localStorage.setItem("access", "1")
  }
  
  printAccess()
}
</script>
