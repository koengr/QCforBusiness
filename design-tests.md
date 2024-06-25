---
title: Design showcase
layout: default
nav_order: 100

accordion: 
  - title: This is Accordion 1
    content: Lorem ipsum dolor sit amet, consectetur adipiscing elit. 

---

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
1. TOC
{:toc}
</details>


{: .gradient-bg }
This is a gradient background part. 


<div class="bg">This is a test!</div>


This is a beautiful main page. 
<img src="/images/image1.jpeg" width="100" />

<script src="https://cdn.mathjax.org/mathjax/latest/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>



Does latex work?

$$ \pi = \frac{1}{2} $$

And inline it goes like \\( 3+3 = \frac{1}{\pi} \\) this.


## Hyperlinks and (base)url

<a href="{{ site.baseurl }}/part1/chapter_2">baseurl href to p1ch2</a> (does not add file extension)

<a href="{{ site.baseurl }}{% link _part2/chapter_1.md %}">baseurl + LINK href to p2ch1</a> (adds file extension)

<a href="{% link _part3/chapter_1.md %}">LINK href to p3ch1</a>

<a href="{{ site.baseurl }}{% link _part3/chapter_2.md %}">baseurl + LINK href to p3ch2</a>



## Tables

Food    | Description                           | Category | Sample type
------- | ------------------------------------- | -------- | -----------
Apples  | A small, somewhat round ...           | Fruit    | Fuji
Bananas | A long and curved, often-yellow ...   | Fruit    | Snow
Kiwis   | A small, hairy-skinned sweet ...      | Fruit    | Golden
Oranges | A spherical, orange-colored sweet ... | Fruit    | Navel
{: .display}

| Priority apples | Second priority | Third priority |
|-------|--------|---------|
| ambrosia | gala | red delicious |
| pink lady | jazz | macintosh |
| honeycrisp | granny smith | fuji |


## Expanding boxes / accordions

{% include accordion.html %}

{% include accordion2.html title="This is accordion2; you can provide the contents inline!" content="For details, see _includes" %}


{% capture details_content %} 
Detailsbox using capture mode 
The **first** line is automatically selected to be the "summary".
\\( 3+3 = \frac{1}{\pi} \\) is great. 
{% endcapture %}

{% include detailsbox.html title="Detailsbox" content=details_content %}


{% include detailsbox.html title="Detailsbox" content="
Alternatively, you can directly specify content...
This is detailsbox.html. It takes the 2nd line as summary header (assuming the 1st line is just '\n'.)

Here is more **text.** 

And math: \\( \pi + \frac{1}{\cos(3)} \\).
Final line. 

" %}

<details>
	<summary> A fancy Details box depending on in-doc CSS </summary>
	Give me attention or face the wrath of my claws give me attention or face the wrath of my claws and pretend not to be evil cats go for world domination allways wanting food. Eat owner's food playing with balls of wool and meow and walk away, and bleghbleghvomit my furball really tie the room together. Cuddle no cuddle cuddle love scratch scratch cat. 
</details>



## "At a glance" header

<fieldset class="field-set" markdown="1">
<legend class="leg-title">TL;DR</legend>
- Show the post in a flexible way.
- Show the figures any place
- Show the maths, the code blocks in a beautiful way.
- and many things else...
</fieldset>


## Fancy buttons

<button type="button" name="button" class="btn">Standard button for GH-pages</button>
<button class="btn">Standard button for GH-pages</button>


<span class="fs-6">
[Bigger button (won't work on GH) -- START READING](ch1){: .btn }
</span>

## Passing arguments to custom templates
{% assign type = 'red' %}
{% include fancybox.html type=type content="
This is a fancy box. **It gives an example** of how to pass arugments to a _include template file.


I was wondering if it works with multiple lines. And maybe even [hyperlinks](google.com)?
" %}


## Colored boxes

<div class="terminal" markdown="1">
`$ sudo apt-get update`
</div>


{: .warning }
See other colored boxes below.

{: .label .label-blue }
Fancy label

red label
{: .label .label-red }

{: .highlight }
Special highlighted text

{: .note-title }
> This is a custom note title
>
> A paragraph with a custom title callout

> {: .new-title }
> > This is a "new" type
> > 
> > red label
> > {: .label .label-red }
> >
> > Another paragraph
> >
> > The last paragraph


