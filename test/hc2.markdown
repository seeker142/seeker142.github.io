---
layout: null
title: Test
permalink: /hc2
exclude: true
---

<p id="top">Your debuff is: <span class="debuff"></span> and <span class="stackdebuff"></span></p>
<p>First tower is: <span class="tower1"></span></p>

<button onclick="randomize()" type="button">
	Randomize</button>

<button onclick="location.href='#ref1'" type="button">
	Start</button>	

<div style="line-height:10000%;"><br></div>




<h2 id="ref1">Stage 1</h2>

<p id="top">Your debuff is: <span class="debuff"></span> and <span class="stackdebuff"></span></p>

What do you do?

<button id="button1_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Go to A

<button id="button1_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Go to B

<button id="button1_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Go to C
	
<button id="button1_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Go to 2
	
<button id="button1_4" class="choice" onclick="location.href='#ref0'" type="button">
	Option 4</button>
Go to 3
	
<div style="line-height:10000%;"><br></div>





<h2 id="ref2">Stage 2</h2>

<p>Your debuff is: <span class="stage2debuff"></span></p>
<p>First tower is: <span class="tower1"></span></p>

What do you do?

<button id="button2_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Do not merge

<button id="button2_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Merge and take tower 1

<button id="button2_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Merge and take tower 2

<button id="button2_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Merge with partner for ifrit
	
<button id="button2_4" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Get hit in the face by cleave

<div style="line-height:10000%;"><br></div>



<h2 id="ref3">Stage 3</h2>

<p>Your debuff is: <span class="stage3debuff"></span></p>
<p>First tower is: <span class="tower1"></span></p>

What do you do?

<button id="button3_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Go to A

<button id="button3_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Go to B

<button id="button3_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Go to C
	
<button id="button3_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Go to the safe area. Avoid merging

<div style="line-height:10000%;"><br></div>



<h2 id="ref4">Stage 4</h2>

<p>Your debuff is: <span class="stage4debuff"></span></p>
<p>Second towers are: <span class="tower2"></span> and <span class="tower3"></span></p>

What do you do?

<button id="button4_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Do not merge

<button id="button4_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Merge with Alpha and enter tower

<button id="button4_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Merge with Beta and enter tower
	
<button id="button4_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Merge with Gamma and enter tower
	
<button id="button4_4" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Bait north add

<button id="button4_5" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Bait west add
	
<button id="button4_6" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Bait east add
	
<button id="button4_7" class="choice" onclick="location.href='#ref0'" type="button">
	Option 4</button>
Bait south add
<div style="line-height:10000%;"><br></div>



<h2 id="ref5">Stage 5</h2>

<p>Your debuff is: <span class="stage5debuff"></span></p>

What do you do?

<button id="button5_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Do not merge

<button id="button5_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Merge with wind

<button id="button5_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Merge with water

<button id="button5_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Merge with lightning

<button id="button5_4" class="choice" onclick="location.href='#ref0'" type="button">
	Option 4</button>
Merge with ifrit

<div style="line-height:10000%;"><br></div>



<h2 id="ref6">SUCCESS</h2>
<button onclick="location.href='#top'" type="button">
	Retry</button>	
<div style="line-height:10000%;"><br></div>



<h2 id="ref0">YOU DIED</h2>
<button onclick="location.href='#top'" type="button">
	Retry</button>	
<div style="line-height:10000%;"><br></div>



<script>
const debuffs = ["Alpha8", "Beta8", "Gamma8", "Alpha28", "Beta28", "Gamma28", "None", "None"];
const stackdebuffs = ["None", "Stack1", "Stack2"];
const towers = ["Wind", "Water", "Lightning"]

debuff = "Alpha8"
stackdebuff = "None"
stage2debuff = "Alpha"
stage3debuff = "Alpha"
stage4debuff = "Alpha"
stage5debuff = "Alpha"
tower1 = "Lightning"
tower2 = "Water"
tower3 = "Wind"

function randomize()
{
	debuff = debuffs[Math.floor(Math.random() * 8)];
	
	stackdebuff = "None";
	if (debuff == "Alpha28" || debuff == "Beta28" || debuff == "Gamma28")
	{
		stackdebuff = stackdebuffs[Math.floor(Math.random() * 3)];
	}
	
	stage2debuff = debuff;
	stage3debuff = debuff;
	stage4debuff = debuff;
	stage5debuff = debuff;

	if (Math.floor(Math.random() * 2) == 0)
	{
		tower1 = "Water";
		tower2 = "Wind";
		tower3 = "Lightning";
	}
	else
	{
		tower1 = "Lightning";
		tower2 = "Wind";
		tower3 = "Water";
	}

	resetChoices();
}

function resetChoices()
{
	var elements = document.getElementsByClassName("choice");
	for (const element of elements) {
		element.outerHTML = element.outerHTML.replace(/ref[0-9]+/, 'ref0');
	}
	
	var elements = document.getElementsByClassName("debuff");
	for (const element of elements) {
		element.innerHTML = debuff;
	}
	
	var elements = document.getElementsByClassName("stackdebuff");
	for (const element of elements) {
		element.innerHTML = stackdebuff;
	}
	
	var elements = document.getElementsByClassName("tower1");
	for (const element of elements) {
		element.innerHTML = tower1;
	}
	
	var elements = document.getElementsByClassName("tower2");
	for (const element of elements) {
		element.innerHTML = tower2;
	}
	
	var elements = document.getElementsByClassName("tower3");
	for (const element of elements) {
		element.innerHTML = tower3;
	}
	
	addCorrectChoices();

	var elements = document.getElementsByClassName("stage2debuff");
	for (const element of elements) {
		element.innerHTML = stage2debuff;
	}

	var elements = document.getElementsByClassName("stage3debuff");
	for (const element of elements) {
		element.innerHTML = stage3debuff;
	}
	
	var elements = document.getElementsByClassName("stage4debuff");
	for (const element of elements) {
		element.innerHTML = stage4debuff;
	}

	var elements = document.getElementsByClassName("stage5debuff");
	for (const element of elements) {
		element.innerHTML = stage5debuff;
	}
}

function setLink(buttonid, link)
{
	element = document.getElementById(buttonid);
	element.outerHTML = element.outerHTML.replace(/ref[0-9]+/, link);
}

function addCorrectChoices()
{
	switch(stackdebuff)
	{
	case "Stack1":
		setLink("button1_4", "ref2");
		break;
	case "Stack2":
		setLink("button1_3", "ref2");
		break;
	}

	switch(debuff)
	{
	case "Alpha8":
		setLink("button1_0", "ref2");

		if(tower1 == "Wind" || tower1 == "Water")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			stage5debuff = stage4debuff;
			setLink("button2_1", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_4", "ref5");
		}
		else
		{
			stage3debuff = "Alpha";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_0", "ref4");
			
			setLink("button4_2", "ref5");
			stage5debuff = "Wind";
		}
		break;
	case "Beta8":
		setLink("button1_1", "ref2");

		if (tower1 == "Lightning")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			stage5debuff = stage4debuff;
			setLink("button2_1", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_4", "ref5");
		}
		else if(tower1 == "Wind")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			stage5debuff = stage4debuff;
			setLink("button2_2", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_7", "ref5");
		}
		else
		{
			stage3debuff = "Beta";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_1", "ref4");

			setLink("button4_1", "ref5");
			stage5debuff = "Wind";
		}
		break;
	case "Gamma8":
		setLink("button1_2", "ref2");

		if(tower1 == "Water" || tower1 == "Lightning")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			stage5debuff = stage4debuff;
			setLink("button2_2", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_7", "ref5");
		}
		else
		{
			stage3debuff = "Gamma";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_2", "ref4");

			setLink("button4_1", "ref5");
			stage5debuff = "Water";
		}
		break;
	
	case "Alpha28":
		setLink("button2_0", "ref3");
		setLink("button3_0", "ref4");

		stage3debuff = "Alpha";
		stage4debuff = stage3debuff;

		if(tower1 == "Lightning")
		{
			setLink("button4_3", "ref5");
			stage5debuff = "Water";
		}
		else
		{
			setLink("button4_2", "ref5");
			stage5debuff = "Wind";
		}

		break;
		
	case "Beta28":
		setLink("button2_0", "ref3");
		setLink("button3_1", "ref4");

		stage3debuff = "Beta";
		stage4debuff = stage3debuff;

		if(tower1 == "Lightning")
		{
			setLink("button4_1", "ref5");
			stage5debuff = "Wind";
		}
		else
		{
			setLink("button4_3", "ref5");
			stage5debuff = "Water";
		}

		break;
		
	case "Gamma28":
		setLink("button2_0", "ref3");
		setLink("button3_2", "ref4");

		stage3debuff = "Gamma";
		stage4debuff = stage3debuff;

		if(tower1 == "Lightning")
		{
			setLink("button4_1", "ref5");
			stage5debuff = "Water";
		}
		else
		{
			setLink("button4_3", "ref5");
			stage5debuff = "Wind";
		}

		break;
		
	case "None":
		setLink("button1_0", "ref2");
		setLink("button2_3", "ref3");
		setLink("button3_3", "ref4");
		setLink("button4_5", "ref5");
		setLink("button4_6", "ref5");
		
		stage2debuff = "Alpha"
		stage3debuff = "Ifrit";
		stage4debuff = "Ifrit";
		stage5debuff = "Ifrit";
		break;
	}
	
	if(stage5debuff == "Ifrit")
	{
		setLink("button5_1", "ref6");
	}
	else if(stage5debuff == "Wind")
	{
		setLink("button5_4", "ref6");
	}
	else
	{
		setLink("button5_0", "ref6");
	}
}

randomize();
</script>