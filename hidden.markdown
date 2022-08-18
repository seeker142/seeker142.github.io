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

<script>		
function localize() {
  console.log(localStorage.getItem("localize"));
  if (localStorage.getItem("localize") === "true") {
    var element = document.getElementsByClassName("post-content e-content")[0];
    element.innerHTML = element.innerHTML.replaceAll('Urushi', 'Jet');
  }
  else {
    var element = document.getElementsByClassName("post-content e-content")[0];
    element.innerHTML = element.innerHTML.replaceAll('Jet', 'Urushi');
  }
}
</script>

<script> localize(); </script>