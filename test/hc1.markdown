---
layout: null
title: Test
permalink: /hc1
exclude: true
---

<p id="top">Your debuff is: <span class="debuff"></span></p>
<p>First tower is: <span class="tower1"></span></p>
<p>Second tower is: <span class="tower2"></span></p>

<button onclick="randomize()" type="button">
	Randomize</button>

<button onclick="location.href='#ref1'" type="button">
	Start</button>	

<div style="line-height:10000%;"><br></div>




<h2 id="ref1">Stage 1</h2>

<p>Your debuff is: <span class="debuff"></span></p>

Debuffs applied. What do you do?

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
<img id="stage2debuffimg" src="">
<p>First tower is: <span class="tower1"></span></p>

First towers appear. What do you do?

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
Get hit in the face by cleave

<div style="line-height:10000%;"><br></div>



<h2 id="ref3">Stage 3</h2>

<p>Your debuff is: <span class="stage3debuff"></span></p>
<img id="stage3debuffimg" src="">
<p>First tower was: <span class="tower1"></span></p>

First towers resolved. What do you do?

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
<img id="stage4debuffimg" src="">
<p>Second tower is: <span class="tower2"></span></p>

Second towers appear. What do you do?

<button id="button4_0" class="choice" onclick="location.href='#ref0'" type="button">
	Option 0</button>
Do not merge

<button id="button4_1" class="choice" onclick="location.href='#ref0'" type="button">
	Option 1</button>
Merge and enter tower 1

<button id="button4_2" class="choice" onclick="location.href='#ref0'" type="button">
	Option 2</button>
Merge and enter tower 2
	
<button id="button4_3" class="choice" onclick="location.href='#ref0'" type="button">
	Option 3</button>
Merge and enter tower 3
	
<button id="button4_4" class="choice" onclick="location.href='#ref0'" type="button">
	Option 4</button>
Merge and enter tower 4
	
<button id="button4_5" class="choice" onclick="location.href='#ref0'" type="button">
	Option 5</button>
Get hit in the face by cleave

<div style="line-height:10000%;"><br></div>



<h2 id="ref5">SUCCESS</h2>
<button onclick="location.href='#top'" type="button">
	Retry</button>	
<div style="line-height:10000%;"><br></div>



<h2 id="ref0">YOU DIED</h2>
<button onclick="location.href='#top'" type="button">
	Retry</button>	
<div style="line-height:10000%;"><br></div>



<script>
const debuffs = ["Alpha8", "Beta8", "Gamma8", "Alpha28", "Beta28", "Gamma28", "Stack2", "Stack3"];
const towers = ["Wind", "Water", "Lightning"]

debuff = "Alpha8"
stage2debuff = "Alpha";
stage3debuff = "Alpha"
stage4debuff = "Alpha"
tower1 = "Wind"
tower2 = "Water"

function randomize()
{
	debuff = debuffs[Math.floor(Math.random() * 8)];
	stage2debuff = debuff;
	stage3debuff = debuff;
	stage4debuff = debuff;
	tower1 = towers[Math.floor(Math.random() * 3)];
	tower2 = towers[Math.floor(Math.random() * 3)];
	
	while(tower1 == tower2)
	{
		tower2 = towers[Math.floor(Math.random() * 3)];
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
	
	var elements = document.getElementsByClassName("tower1");
	for (const element of elements) {
		element.innerHTML = tower1;
	}
	
	var elements = document.getElementsByClassName("tower2");
	for (const element of elements) {
		element.innerHTML = tower2;
	}
	
	addCorrectChoices();
	setImages();

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
}

function setLink(buttonid, link)
{
	element = document.getElementById(buttonid);
	element.outerHTML = element.outerHTML.replace(/ref[0-9]+/, link);
}

function addCorrectChoices()
{
	switch(debuff)
	{
	case "Alpha8":
		setLink("button1_0", "ref2");
		stage2debuff = "Alpha";

		if(tower1 == "Wind" || tower1 == "Water")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			setLink("button2_1", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_0", "ref5");
		}
		else
		{
			stage3debuff = "Alpha";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_0", "ref4");
			if(tower2 == "Wind" || tower2 == "Water")
			{
				setLink("button4_1", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		break;
	case "Beta8":
		setLink("button1_1", "ref2");
		stage2debuff = "Beta";

		if (tower1 == "Lightning")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			setLink("button2_1", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_0", "ref5");
		}
		else if(tower1 == "Wind")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			setLink("button2_2", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_0", "ref5");
		}
		else
		{
			stage3debuff = "Beta";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_1", "ref4");
			if(tower2 == "Lightning")
			{
				setLink("button4_1", "ref5");
			}
			else if(tower2 == "Wind")
			{
				setLink("button4_2", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		break;
	case "Gamma8":
		setLink("button1_2", "ref2");
		stage2debuff = "Gamma";

		if(tower1 == "Water" || tower1 == "Lightning")
		{
			stage3debuff = tower1;
			stage4debuff = stage3debuff;
			setLink("button2_2", "ref3");
			setLink("button3_3", "ref4");
			setLink("button4_0", "ref5");
		}
		else
		{
			stage3debuff = "Gamma";
			stage4debuff = stage3debuff;
			setLink("button2_0", "ref3");
			setLink("button3_2", "ref4");
			if(tower2 == "Water" || tower2 == "Lightning")
			{
				setLink("button4_2", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		break;
	
	case "Alpha28":
		setLink("button1_3", "ref2");
		setLink("button2_0", "ref3");
		setLink("button3_0", "ref4");

		stage4debuff = "Alpha";
		if(tower2 == "Wind" || tower2 == "Water")
		{
			setLink("button4_3", "ref5");
		}
		else
		{
			setLink("button4_0", "ref5");
		}
		break;
		
	case "Beta28":
		setLink("button1_4", "ref2");
		setLink("button2_0", "ref3");
		setLink("button3_1", "ref4");

		stage4debuff = "Beta";
		if(tower2 == "Lightning")
		{
			setLink("button4_3", "ref5");
		}
		else if(tower2 == "Wind")
		{
			setLink("button4_4", "ref5");
		}
		else 
		{
			setLink("button4_0", "ref5");
		}
		break;
		
	case "Gamma28":
		setLink("button1_4", "ref2");
		setLink("button2_0", "ref3");
		setLink("button3_2", "ref4");

		stage4debuff = "Gamma";
		if(tower2 == "Water" || tower2 == "Lightning")
		{
			setLink("button4_4", "ref5");
		}
		else 
		{
			setLink("button4_0", "ref5");
		}
		break;
		
	case "Stack2":
		setLink("button1_3", "ref2");
		setLink("button2_0", "ref3");
		stage2debuff = "None (Stack2)";
		stage3debuff = "None (Stack2)";
		
		if(tower1 == "Wind" || tower1 == "Water")
		{
			setLink("button3_0", "ref4");
			stage4debuff = "Alpha";
			
			if(tower2 == "Wind" || tower2 == "Water")
			{
				setLink("button4_1", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		else 
		{
			setLink("button3_1", "ref4");
			stage4debuff = "Beta";
			
			if(tower2 == "Lightning")
			{
				setLink("button4_1", "ref5");
			}
			else if(tower2 == "Wind")
			{
				setLink("button4_2", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		break;

	case "Stack3":
		setLink("button1_4", "ref2");
		setLink("button2_0", "ref3");
		stage2debuff = "None (Stack3)";
		stage3debuff = "None (Stack3)";
		
		if(tower1 == "Wind")
		{
			setLink("button3_1", "ref4");
			stage4debuff = "Beta";
			
			if(tower2 == "Lightning")
			{
				setLink("button4_1", "ref5");
			}
			else if(tower2 == "Wind")
			{
				setLink("button4_2", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		else 
		{
			setLink("button3_2", "ref4");
			stage4debuff = "Gamma";
			
			if(tower2 == "Water" || tower2 == "Lightning")
			{
				setLink("button4_2", "ref5");
			}
			else
			{
				setLink("button4_0", "ref5");
			}
		}
		break;
	
	}
}

alphaimg = "https://img.game8.jp/7227090/3cf16a9de5ac1e02a65341cea2a66cff.png/show"
betaimg = "https://img.game8.jp/7227091/b5535057bfdad7f3d41abd9d7621cb46.png/show"
gammaimg = "https://img.game8.jp/7227092/41d883e4dc9ad6fb0d5db46a7fce2cb7.png/show"
windimg = "https://img.game8.jp/7227094/e48a0793fb45eca6cf9e4c737d558986.png/show"
waterimg = "https://img.game8.jp/7228918/d24eebe86572b804eb40165e866255ec.png/show"
lightningimg = "https://img.game8.jp/7227096/4a417a62006dd25df0170d6f5b21bfd4.png/show"
ifritimg = "https://img.game8.jp/7227095/9b5a04388a6940eb7f6179b729396bbc.png/show"

function getImage(debuff)
{
	imglink = ""
	
	if(debuff == "Alpha")
	{
		imglink = alphaimg;
	}
	else if(debuff == "Beta")
	{
		imglink = betaimg;
	}
	else if(debuff == "Gamma")
	{
		imglink = gammaimg;
	}
	else if(debuff == "Water")
	{
		imglink = waterimg;
	}
	else if(debuff == "Wind")
	{
		imglink = windimg;
	}
	else if(debuff == "Lightning")
	{
		imglink = lightningimg;
	}
	else if(debuff == "Ifrit")
	{
		imglink = ifritimg;
	}
	
	return imglink;
}

function setImages()
{
	element = document.getElementById("stage2debuffimg");
	element.src = getImage(stage2debuff);
	
	element = document.getElementById("stage3debuffimg");
	element.src = getImage(stage3debuff);
	
	element = document.getElementById("stage4debuffimg");
	element.src = getImage(stage4debuff);	
}

randomize();
</script>