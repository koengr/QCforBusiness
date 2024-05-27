---
title: Home
layout: home
nav_order: 0

accordion: 
  - title: Why would I read this detail?
    content: Lorem ipsum dolor sit amet, consectetur adipiscing elit. 

---
This is a beautiful main page. 

![image tooltip here](/media/image1.jpeg)

## Expanding boxes / accordions

{% include accordion.html %}

{% include accordion2.html title="This is accordion2; you can provide the contents inline!" content="For details, see _includes" %}

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
