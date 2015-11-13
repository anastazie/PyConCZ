---
title       : Using Django for Genome Engineering
author      : Anastassiya Zidkova, Filip Sedlak
framework   : impressjs       # {io2012, html5slides, shower, dzslides, ...}
highlighter : highlight.js  # {highlight.js, prettify, highlight}
hitheme     : tomorrow      # 
widgets     : []            # {mathjax, quiz, bootstrap}
mode        : selfcontained # {standalone, draft}
knit        : slidify::knit2slides
---
<link rel="stylesheet" href="highlight/styles/default.css">
<script src="highlight/highlight.pack.js"></script>
<script>hljs.initHighlightingOnLoad();</script>

<style type="text/css">

.centeredText {
    text-align:center;
    margin-top:0px;
    margin-bottom:0px;
    padding:0px;
}

.centeredImage {
    display: block;
    margin: 0 auto;
}

.centeredCode {
  text-align:center;
  margin-top:0px;
  margin-bottom:0px;
  padding:0px;
  font-family:     "Courier New"
                    Courier
                    monospace;
}

.code {
  font-family:     "Courier New"
                    Courier
                    monospace;
}

body {
    background: #9DB1DC;
}

</style>

--- #title x:0 y:0 

<p style="font-size:40px" class="centeredText"><b> Using Django for Genome Engineering </b> </p>
<p style="font-size:38px; margin-top: 10px" class="centeredText"> Anasstassiya Zidkova, Filip Sedlák </p>
<img src="logo-merck-white.png" style="margin-top: 20px" class="centeredImage">

--- #slide1 x:700 y:-800 scale:0.5
<p style="font-size:26px" class="centeredText"> Most of us like to play cars </p>
<img src="child-car.jpg"class="centeredImage"  height="500">
<p style="font-size:16px"  class="centeredText"> http://nspt4kids.com/parenting/developmental-skills-while-playing-with-cars/ </p>


--- #slide2 x:-100 y:-1000 rot:-90
<p style="font-size:30px" class="centeredText"> Some of us like to diassemble cars ... </p>
<img src="disassembleCar.jpg" class="centeredImage" height="500">
<p style="font-size:30px" class="centeredText"> ... in order to study how they work </p> </br>
<p style="font-size:16px" class="centeredText"> http://imgur.com/gallery/DEJwM </p>


--- #slide3 x:-1000 y:-600 rotx:60 roty:-60 rotz:90
<p style="font-size:30px" class="centeredText"> Can we use the same approach to study living organisms? </p>
<img src="seal.jpg" class="centeredImage">
<p style="font-size:16px" class="centeredText"> http://vignette4.wikia.nocookie.net/lesmiserables/images/6/6b/Awww-cute-seal-white-snow.jpg </p>

--- #slide4 x:-1000 y:400 scale:0.25
<p style="font-size:30px" class="centeredText">Now let's make a short intro into genetics ... </p>

--- #slide5 x:-1200 y:1000 rot:-45 scale:0.5
<img src="intro.jpg" class="centeredImage">

--- #slide6 x:200 y:1000 rot:90 scale:1
<div style="background-color: white">
    <img src="chromosome.png" class="centeredImage"  style="width: 50%; height: 50%">
    <p style="font-size:16px" class="centeredText"> http://www.yourgenome.org/facts/what-is-a-chromosome </p>
</div>

--- #slide7 x:1400 y:1000 z:500 scale:0.5
<img src="intro2.jpg" class="centeredImage">

--- #slide8 x:2500 y:500 z:500 scale:0.5
<p style="font-size:30px" class="centeredText"> I remember you! </p>
<img src="finger.jpg" class="centeredImage" style="width: 50%; height: 50%"></a></p>
<p style="font-size:16px" class="centeredText"> https://creativemarket.com/microvector/109424-Retro-pointing-finger </p>

--- #slide9 x:2500 y:-800  scale:1.5
<p style="font-size:30px" class="centeredText">  How it works ... </p>
<img src="intro3.jpg" class="centeredImage">

--- #slide10 x:800 y:-1500  rot:45 scale:0.25
<img src="crispr2.jpg" class="centeredImage">
<p style="font-size:16px" class="centeredText"> http://synbiobeta.com/caribou-biosciences-raises-11-million-series-a/ </p>

--- #slide11 x:-200 y:-1800 z:500 scale:0.5
<img src="intro4.jpg" class="centeredImage">

--- #slide12 x:-1200 y:-2000 scale:1 rot:-90
<img src="mismatch.png" class="centeredImage">


--- #slide13 x:-2000 y:-1200 scale:0.5 rotz:-90
<img src="communication.png" class="centeredImage">

--- #slide14 x:-3500 y:-200 z:500 scale:1
<pre style="font-size:30px" class="centeredCode"><code>
A -> 01000001 -> 00
G -> 01000111 -> 01
C -> 01000011 -> 10
T -> 01010100 -> 11
</code></pre>

--- #slide15 x:-2500 y:1000 z:-500 scale:0.25 rot:30
<pre style="font-size:25px" class="code"><code class="python">
def make_byte(four_letters):
    letters = {
        "A": 0b00, 
        "G": 0b01, 
        "C": 0b10, 
        "T": 0b11
    }
    return sum(
        [letters[letter] << (2 * i) 
            for i, letter 
            in enumerate(four_letters)])
            
            
&gt;&gt;&gt; hex(make_byte("ACTA"))
'0x38'
</code></pre>


--- #slide16 x:-3500 y:1500 z:1000 scale:0.1 rot:-90
<img src="berkeley.jpg" class="centeredImage" style="width: 99%;">

--- #slide17 x:-2500 y:2500 z:1000 scale:0.1 rot:90
<img src="makefile.jpg" class="centeredImage" style="width: 99%;">

--- #slide18 x:-1500 y:2500 z:500 rot:180 scale:2
<img src="genome_scan.jpg" class="centeredImage">

--- #slide19 x:0 y:3500 scale:0.25
<img src="django.jpg" class="centeredImage" style="width: 99%;">

--- #slide20 x:1500 y:2500 rotz:90
<img src="webapp.png" class="centeredImage" style="width: 99%;">

--- #slide21 x:2000 y:1800 z:1000 scale:0.4 rotz:-90
<img src="webappGenSearch.png" class="centeredImage" style="width: 99%;">

--- #slide22 x:3500 y:3500 z:1000 scale:1 
<img src="python.jpg" class="centeredImage">
<p style="font-size:16px" class="centeredText"> Wikipedia </p>

--- #slide23 x:3500 y:2500 z:1000 scale:0.5
<img src="happy-scientist.jpg" class="centeredImage">
<p style="font-size:16px" class="centeredText"> https://heywhatwhatdidyousay.files.wordpress.com/2013/06/happy-scientist.jpg </p>

--- #slide24 x:3500 y:1500 z:1000 scale:1 rot:360 
<p style="font-size:30px" class="centeredText"> THANK YOU FOR ATTENTION!</p>


