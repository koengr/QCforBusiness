---
title: About
layout: default
nav_order: 1
nav_exclude: false
---

## About Introduction to Quantum Computing for Business


<style>
/* Credits to https://codepen.io/jeongmin-kim-the-flexboxer/pen/VwVqxRO */

.book-container {
    margin: 3em ;

}
.book-3d {
  --book-thickness: 20px;
  /* --cover-color: #1c67a2ff; */
  --cover-color:rgba(28, 104, 162, 0.83);

	perspective: 1000px;
  max-width: 250px;
  margin: 1em auto;
  margin-bottom: 4em;

}

.book-3d__inner {
	position: relative;
	transform-style: preserve-3d;
    transform: rotateY(-25deg)
}

/* Book Pages */
.book-3d__inner::before {
  position: absolute;
  content: ' ';
  left: 100%;
  top: 1%;
  width: calc( var(--book-thickness) * 2 );
  height: 98%;
  transform: translate(-55%,0) rotateY( 90deg );
  background: linear-gradient( 90deg , #fff 0%, hsl(0, 0%, 94%) 5%, #fff 10%, hsl(0, 0%, 94%) 15%, #fff 20%, hsl(0, 0%, 94%) 25%, #fff 30%, hsl(0, 0%, 94%) 35%, #fff 40%, hsl(0, 0%, 94%) 45%, #fff 50%, hsl(0, 0%, 94%) 55%, #fff 60%, hsl(0, 0%, 94%) 65%, #fff 70%, hsl(0, 0%, 94%) 75%, #fff 80%, hsl(0, 0%, 94%) 85%, #fff 90%, hsl(0, 0%, 94%) 95%, #fff 100% );
}

/* Rear Cover */
.book-3d__inner::after {
  content: '';
  position: absolute;
  top: 0;
  left: 1%;
  width: 100%;
  height: 100%;
  transform: translateZ( calc( var(--book-thickness) * -1 ) );
  background-color: var(--cover-color);
  border-radius: 0 2px 2px 0;
  box-shadow: 0px 0px 20px 34px rgba(117, 74, 55, 0.0), 24px 15px 20px 0px rgba(61, 61, 61, 0.64);
}

.book-3d__cover {
  display:block;
  width:100%;
  height: auto;
  border-radius: 0px 2px 2px 0px;
  transform: translateZ( var(--book-thickness) );
  box-shadow: 0px 0px 20px 0px rgba(0, 0, 0, 0.40);
  /* filter: drop-shadow(1px 2px 40px hsl(220deg 00% 00%) ); */
  
}
</style>

<div class="book-container">
<div class="book-3d">
  <div class="book-3d__inner">
    <img class="book-3d__cover" src="/site-img/cover-small.png" alt="Cover of book">
  </div>
</div>
</div>

How will businesses use quantum technology in the future? What problems will a quantum computer solve? How long will it take before these devices become commercially relevant?

With the first generation of quantum computers on the horizon, understanding their impact is more relevant than ever. Luckily, you don't need a physics degree to understand the functionality of these computers – just like you don't need to know how a transistor works to excel in conventional IT. 

This book is the perfect introduction to the opportunities and threats of quantum technologies. It equips you with the necessary knowledge to join cutting-edge discussions and make strategic decisions.  

*Easy to read and full of insights, a must-read for anyone looking to understand the real-world impact of quantum computing.* - **Diederick Croese, Director of Center for Quantum and Society**

*This book offers a well-rounded, scientifically accurate overview of quantum technology, highlighting its significant potential for innovation.* - **Christian Schaffner, Professor in Theoretical Computer Science, Director of QuSoft**

## About *Intro To Quantum*

Through [www.IntroToQuantum.org](https://www.introtoquantum.org), the book is available for everyone to read, conveniently from your webbrowser, including plenty of useful links to other resources. 

Do you prefer a printed version? A paperback will be released soon! 

## About the author

<img src="https://www.uva.nl/binaries/_ht_1728037267798/content/documents/personalpages/g/r/k.l.groenland/k.l.groenland" alt="Koen Groenland on IntroToQuantum.org" style="width:200px; border-radius:15px; margin-top:40px">

Koen Groenland is a theoretical physicist with a PhD in the near-term applications of quantum computers. He works as an innovation officer at the University of Amsterdam, where he is responsible for setting up research collaborations and developing lifelong learning education for professionals. He is one of the driving forces behind Quantum.Amsterdam, the innovation hub that drives the commercialisation of quantum technologies around the Dutch capital.
