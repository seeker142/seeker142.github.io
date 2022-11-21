---
layout: page
title: Hidden Settings
permalink: /hidden/
exclude: true
---

Click this if you have bad taste: <button onclick="localizeToggle()">Localize Toggle</button>

<div id="result"></div>
<script>
if (typeof(Storage) === "undefined") {
  document.getElementById("result").innerHTML = "Sorry, your browser does not support web storage.";
}
</script>

<div class="post-content e-content">
<p>Master: A man from Japan that was reincarnated as a sword. Named by Fran.</p>
<p>Urushi: A wolf familiar summoned by Master. Skilled in the use of dark magic.</p>
</div>


<script>
function localizeToggle()
{
  if (localStorage.getItem("localize") &&
  	localStorage.getItem("localize") === "true")
  {
    localStorage.setItem("localize", "false")
  }
  else
  {
    localStorage.setItem("localize", "true")
  }
  
  localize();
}
</script>

{%- include localize.html -%}
