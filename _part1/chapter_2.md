---
layout: default
title: 2 The background, why are we so enthusiastic about Quantum Technology?
nav_order: 2
---


### What is Quantum?  

**Quantum Physics** is the theory that describes the smallest particles,
like electrons, atoms, and sometimes even small molecules. It's the
machinery that describes things that happen at the scale of nanometers.
You may contrast it to Newton's classical physics, which works great for
objects that are the size of a human, but becomes inaccurate at much
smaller scales. Quantum is, in a sense, a *refinement *of classical
physics: the theories agree for large objects, but one requires the more
difficult quantum theory to describe small things. 

It should not come as a surprise that quantum physics is relevant for
several kinds of technology that operate on a small scale,
like [nano-cars that consist of just a few
atoms](https://www.rug.nl/news/2019/12/molecular-motors-and-switches?lang=en),
or [ever-smaller transistors on computer
chips](https://www.nature.com/articles/nature.2012.9747). However,
quantum technology goes further than simply telling us how to handle
small particles: **quantum allows us to perform certain processes in a
fundamentally different way. **We will see an insightful example of this
very soon. 

In particular, we will refer to 'classical' technology to mean devices
that don't carefully exploit the possibilities of quantum physics. For
example, you're most likely reading this on a classical computer or
phone right now, using the classical internet. Whereas classical
computers work with 'bits', quantum technology will store information in
something called 'quantum bits', or shortly 'qubits'. Generally, under
the nomer of **quantum technology**, we distinguish four categories:

\-\-- Begin fancy comparison table:

Quantum Computers

Devices that use quantum physics to perform automatic calculations in
order to solve a certain problem. Computing is the main focus of this
blog. 

Quantum Networks

A connection between quantum devices over which *qubits *can be
transmitted. The most relevant use case is to strengthen cryptography
used by classical computers, but there are many more applications.

Quantum Sensors

Devices that exploit quantum-mechanical effects to accurately measure
certain quantities, like a magnetic field or the strength of the earth's
gravity. Quantum clocks also fall in this category. 

Quantum Simulators

Devices that carefully reproduce the behaviour of atoms and electrons in
a piece of material, allowing us to understand the properties of said
material. 

\-\-- End comparison table

In this blog, we mainly focus on **computers **and **internet**: simply
because these will have the biggest impact on typical (business) users.
If you'd like to know more about the technical details, we recommend the
following sources as a great introduction: 

-   [Quantum Country](http://new.quantum.country/) -- a great online
    textbook about Quantum Computing by Andy Matuschak and Michael
    Nielsen.

-   [QuTech Academy's ](https://www.qutube.nl/)*[School of
    Quantum]{.underline} -- *A broad range of topics explained using
    short videos. 

-   [The Map of Quantum Computing
    (Youtube)](https://www.youtube.com/watch?v=-UlxHPIEVqA)  -- A
    30-minute video that forms a great supplement to this blog. 

### What can Quantum Technologies do for us? 

Quantum computers are devices that perform automatic computations at our
command, very much like their classical counterparts. The 'quantum' part
stems from the fact that it can actually exploit the laws of quantum
mechanics. This should be contrasted to our conventional 'classical'
computers, which technically can also be completely described by quantum
mechanics, but they just happen to also work fine according to classical
physics. By no means are they supposed to ever deal with quantum
phenomena
like [superposition](https://en.wikipedia.org/wiki/Quantum_superposition) or [entanglement](https://en.wikipedia.org/wiki/Quantum_entanglement).
Contrarily, a proper quantum computer does exploit these purely quantum
mechanical effects. 

A naive view of quantum computers is that they're simply *faster* than
their conventional cousins. Or perhaps one may naively point at Moore's
Law: with transistors reaching atomic scales, we run into quantum
effects, hence quantum physics may help us make better chips. However,
none of these are our core motivation to look at quantum computers. 

Firstly, **quantum computers are much, much slower than conventional
computers,** if one focuses on their 'time to perform a basic step'. A
modern CPU can handle 64-bit numbers (meaning that all numbers between 0
and 2^64^-1= 18,446,744,073,709,551,615 can be represented). It can
perform basic arithmetic like addition, multiplication, and so forth on
these numbers, essentially in one single 'step'. The speed of a modern
CPU is incredible: a typical Intel or AMD processor bought in 2022
performs these steps at roughly 4 GHz , i.e., 4 billion steps per
second. There's no way a human can possibly keep up with such speeds
when it comes to plain calculations! 

Now, quantum computers are supposed to be even faster, right? Well, it's
not hard to find backing for that claim: 

-   [Google creates quantum chip millions of times faster than the
    fastest
    supercomputer](https://www.techradar.com/news/google-creates-quantum-chip-millions-of-times-faster-than-the-fastest-supercomputer)

-   [Chinese Scientists Create Quantum Processor 60,000 Times Faster
    Than Current
    Supercomputers](https://www.iflscience.com/technology/chinese-scientists-create-quantum-processor-60000-times-faster-than-current-supercomputers/)

 

However, you may be disappointed to hear that quantum computers, at this
moment, cannot even add or multiply numbers of more than 3 or 4 bits.
And even if they could, their rate of operation would by no means reach
4 GHz, but more likely several MHz (a few million operations per
second), at best. In other words, they're more than a thousand
times *slower. *To make things worse, the information in quantum
computers is extremely fragile and requires to be constantly checked and
corrected, using so-called **error correction***. *This is a form of
overhead that could make quantum computers another several orders of
magnitude slower. Even in the far future, when quantum computers are
more mature and more reliable, we still expect them to be much slower
than the classical chips at that time. 

How does this rhyme with the news about ever faster quantum computers?
And why are we still interested in these slow machines? As we claimed
before, we hope to do certain computations in a **fundamentally
different way**. We borrow the following analogy from Andy Matuschak and
Michael Nielsen's [Quantum.country](https://quantum.country/). 

![The Strait of
Gibraltar](/media/image1.jpeg){width="3.8614195100612423in"
height="3.8229166666666665in"}Image source:
https://commons.wikimedia.org/wiki/File:STS059-238-074_Strait_of_Gibraltar.jpg

Imagine that you'd like to travel from Morocco to Spain. If your
technology does not allow you to cross the Strait of Gibraltar (say, you
only have a car or a bike), your only choice is to traverse all the way
through North-Africa, past the Arabian Peninsula, and through Europe,
before you can reach your destination. This represents the steps taken
by a classical algorithm. In the same analogy, a quantum computer endows
you with the ability to traverse the sea at the Strait of Gibraltar
(like a hovercraft). The fundamentally new possibilities that quantum
offers allow us to do computations in *fewer steps*: even with a slower
vehicle (computer), one may arrive at the destination sooner. In fact,
this advantage often grows as problems become larger and more
complicated. It is still an active area of research to completely map
the landscape over which quantum computers can travel, and hence to
determine which problems can be sped up, and which cannot. 

We like this analogy in particular, because it indicates that **some
problems can profit greatly from a quantum computer, whereas many
won't**: you would not want to travel by hovercraft from Amsterdam to
Berlin. For this reason, we don't expect that classical computers will
be 'replaced' any time soon: instead, different types of processors
(classical, quantum) should synergize and work together to solve a
problem as efficiently as possible.

In the analogy with the Strait of Gibraltar, the precise 'route' that
you travel is the **algorithm. **More precisely, an algorithm is
a **step-by-step list of instructions** that guarantee a human or a
computer to find the solutions. The '*steps' *here should be
sufficiently simple so that it is completely unambiguously how to do
them: for example, adding, multiplying or comparing numbers. A **quantum
algorithm** has a wider spectrum of allowed 'steps', as made possible by
a quantum computer. In the end, simply finding the 'recipe' itself is
not enough: the algorithm has to be turned into **quantum software**, a
piece of computer code that tells a computer explicitly how to execute
the step-by-step instructions, given the possibilities and limitations
of the computer hardware.

The difference between 'algorithms' and 'software' is subtle: you may
think of the algorithm as a recipe to bake the perfect chocolate cookie.
The algorithm should unambiguously describe the required steps to bake
the cookie: what ingredients are needed, in what order they should be
mixed, how long the cookie should be baked, etcetera. However, if you'd
like to build a factory that produces these cookies, you need to be even
more specific: out of what pipe does the dough flow, and in what pot
does it have to be mixed? What exactly is the tool that performs the
mixing? How are cookies laid next to each other in the oven?

Hence, the 'algorithm' is a very general solution to a problem: once
found, it can be re-used different times, by different software
developers. The 'software' is specific to a (type of) computer (here:
the 'factory'). 

In the next part, we'll dive into precisely what **quantum
algorithms **are known, and how much impact these will have.

