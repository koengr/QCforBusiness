---
title: Introduction to Quantum Computing for Business
layout: default
nav_order: 0
nav_exclude: true
---

<!-- <img src=" {{ site.baseurl }}/site-img/header-logo.webp" width="700" /> -->


<!-- <h1 style="font-size:30px !important; margin-bottom:1em;"> Introduction to Quantum Computing for Business </h1> -->

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
  top: 0%;
  width: calc( var(--book-thickness) * 2 );
  height: 100%;
  transform: translate(-55%,0) rotateY( 90deg );
  background: linear-gradient( 90deg , #fff 0%, hsl(0, 0%, 94%) 5%, #fff 10%, hsl(0, 0%, 94%) 15%, #fff 20%, hsl(0, 0%, 94%) 25%, #fff 30%, hsl(0, 0%, 94%) 35%, #fff 40%, hsl(0, 0%, 94%) 45%, #fff 50%, hsl(0, 0%, 94%) 55%, #fff 60%, hsl(0, 0%, 94%) 65%, #fff 70%, hsl(0, 0%, 94%) 75%, #fff 80%, hsl(0, 0%, 94%) 85%, #fff 90%, hsl(0, 0%, 94%) 95%, #fff 100% );
}

/* Rear Cover */
.book-3d__inner::after {
  content: '';
  position: absolute;
  top: 0;
  left: 0%;
  width: 100.2%;
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


/**
 * Pen Specific Styles
 * ===================
*/

/* *, *::before, *::after {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
} */



</style>

<div class="book-container">
<div class="book-3d">
  <div class="book-3d__inner">
    <img class="book-3d__cover" src="/site-img/cover-small.png" alt="Cover of book">
  </div>
</div>
</div>



**Introduction to Quantum Computing for Business** is an open-access book that contains everything you should know about quantum technologies, without going into tedious technical details. It answers questions such as:

- What is a quantum computer or a quantum network? What are their [applications]({% link _essentials/applications-overview.md %})?

- In [what year]({% link _essentials/timelines.md %}) will we have large-scale quantum computers?

- What are the consequences for [cybersecurity]({% link _applications/cybersecurity.md %}) ?

- What [strategic actions]({% link _advanced/strategic-actions.md %}) should organisations take? 

- What is the status of today's [hardware]({% link _advanced/hardware.md %})?
<br>

As the first generation of quantum computers is on the horizon, understanding their impact is more important than ever. Luckily, you don't need a physics degree to understand their functionality - just like you don’t need to know how a transistor works to thrive in conventional IT. 

This book, written by [Koen Groenland](https://www.koengroenland.com), is a gentle and business-oriented introduction to the opportunities and threats of quantum technologies. It equips you with the necessary knowledge to join cutting-edge discussions and to make strategic decisions. 

<center>
<a href="{{ site.baseurl }}/essentials/preface"><button class="btn fs-5 btn-outline" style="padding:1em;">Start reading > </button></a>
</center>

📖 Prefer to read a printed version? A paperback edition will be released on [18 March 2025](https://www.aup.nl/en/book/9789048568987/introduction-to-quantum-computing-for-business).
