---
layout: default
title: 3 The background, why are we so enthusiastic about Quantum Technology?
nav_order: 3
---

## The background: why are we so enthusiastic about Quantum Technology? 

<fieldset class="field-set" markdown="1"> 
<legend class="leg-title">At a glance</legend>

Quantum technology is an umbrella term for devices that exploit quantum
phenomena like superposition and entanglement. The most notable
innovations are expected in computers, networks, sensors, and
simulators.

Quantum computers will be much slower than conventional computers. Their
advantage comes from the ability to run quantum algorithms, which solve
specific problems in much fewer steps.

</fieldset>

### What is quantum technology?

Quantum physics has already proven itself as an invaluable basis for
technologies such as LED lighting, MRI scanners and solar cells. And
it's still relevant to push the limits of innovation, with nano-cars
that consist of just a few atoms, or ever-smaller transistors on
computer chips on the horizon.

Just ahead of us is a new paradigm, which we'll call quantum technology.
The distinguishing factor is that it goes further than merely building
stuff from small particles. Quantum technology is about devices that
perform certain processes in a fundamentally different way. That is, the
data (or operations) we work with can have special properties unique to
quantum physics, such as superposition and entanglement.

In our jargon, we will refer to 'classical' technology to mean devices
that don't carefully exploit the possibilities of quantum physics. Your
laptop and phone are examples of classical computers, and they're
connected to the classical internet. The internal transistors and
electrical circuits might be so tiny that quantum physics surely is
relevant there, but the fundamental point is that the information that
they process is purely classical. Whereas classical computers work with
'bits', quantum technology will store information in something called
'quantum bits', or shortly 'qubits'. Generally, under the nomer
of **quantum technology**, we distinguish four categories:

{{ begin comparison table }}

Quantum Computers

Quantum computers are devices that use quantum physics to perform
automatic calculations to solve a problem. Computing is considered the
most impactful application for most organisations, and therefore, it's
the main focus of this book. 

Quantum Networks

Quantum networks are connections between quantum devices over
which *qubits* (or similar forms of quantum data)* *can be transmitted.
The most relevant use case is to strengthen cryptography used by
classical computers, but there are many more applications.

Quantum Sensors

Quantum sensors are devices that exploit the effects of quantum physics
to accurately measure certain quantities, such as a magnetic field or
the strength of the earth's gravity. Quantum clocks also fall into this
category. 

Quantum Simulators

Quantum simulators are devices similar to quantum computers, except that
they specialise in solving a limited set of problems. Typically, they
are built to reproduce the behaviour of atoms and electrons in a
molecule or a piece of material, allowing us to measure properties like
energies and reaction rates.

{{ end comparison table }}

In this blog, we mainly focus on **computers **and **networks**: simply
because these seem to have the biggest impact on typical (business)
users.

### Why can quantum computers have an advantage? 

Quantum computers are devices that perform automatic computations at our
command, very much like their classical counterparts. The 'quantum' part
stems from the fact that it can actually exploit the laws of quantum
mechanics. This should be contrasted to our conventional 'classical'
computers, which technically can also be completely described by quantum
mechanics, but they just happen to also work fine according to classical
physics. By no means are they supposed to ever deal with quantum
phenomena like superposition or entanglement. Contrarily, a proper
quantum computer does exploit these purely quantum mechanical effects. 

A naive view of quantum computers is that they're simply *faster* than
their conventional cousins. Or perhaps one may naively point at Moore's
Law: with transistors reaching atomic scales, we run into quantum
effects, hence quantum physics may help us make better chips. However,
none of these are our core motivation to look at quantum computers. 

Firstly, **quantum computers are much, much slower than conventional
computers,** if one focuses on their 'time to perform a basic step'. A
modern CPU can handle 64-bit numbers (meaning that all numbers between 0
and 2^64^-1= 18,446,744,073,709,551,615 can processed in a single step).
It can perform basic arithmetic like addition, multiplication, and so
forth on these numbers, essentially in one single 'step'. The speed of a
modern CPU is incredible: a modern Intel or AMD processor works at a
rate of several GHz, that is, several billions of steps per second.
There's no way a human can possibly keep up with such speeds when it
comes to plain calculations! 

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
several GHz, but more likely several MHz (a few *million* operations per
second), at best. In other words, they're more than a thousand
times *slower. *To make things worse, the information in quantum
computers is extremely fragile and requires to be constantly checked and
corrected, using so-called **error correction***. *This is a form of
overhead that could make quantum computers another several orders of
magnitude slower. Even in the far future, when quantum computers are
more mature and more reliable, we still expect them to be much slower
than the classical chips at that time. 

How does this rhyme with the news about ever-faster quantum computers?
And why are we still interested in these slow machines? As we claimed
before, we hope to do certain computations in a **fundamentally
different way**. Let's look at the following analogy that Andy Matuschak
and Michael Nielsen bring up in their online course Quantum.country. 

![The Strait of
Gibraltar](/media/image7.jpeg){width="3.8614195100612423in"
height="3.8229166666666665in"}Image source:
https://commons.wikimedia.org/wiki/File:STS059-238-074_Strait_of_Gibraltar.jpg

Imagine that you'd like to travel from Morocco to Spain. If your
technology does not allow you to cross the Strait of Gibraltar (say, you
have access to a car but not a boat), then you'd need to take an
incredible detour: all the way through North Africa, past the Arabian
Peninsula, and through Europe, before you can reach your destination.
This represents the steps taken by a classical algorithm. In the same
analogy, a quantum computer grants you the ability to traverse both land
and sea (much like a hovercraft). The fundamentally new possibilities
that quantum offers allow us to do computations in *fewer steps*: even
with a slower vehicle (computer), one may arrive at the destination
sooner. In fact, this advantage often grows as problems become larger
and more complicated. It is still an active area of research to
completely map the landscape over which quantum computers can travel
and, hence, to determine which problems can be sped up and which
cannot. 

I like this analogy because it indicates that some problems can profit
greatly from a quantum computer, whereas many won't: you would not want
to travel by hovercraft from Amsterdam to Berlin. For this reason, we
don't expect that classical computers will be 'replaced' any time soon:
instead, different types of processors (CPUs, GPUs, quantum computers)
are expected to co-exist. GPU and Quantum Processing Units (QPUs) are
special-purpose devices, meant to only do tricks that they happen to be
good at.

In the analogy with the Strait of Gibraltar, the precise 'route' that
you travel is the **algorithm. **More precisely, an algorithm is
a step-by-step list of instructions that describes how a computational
problem should be solved. The 'steps'* *here should be sufficiently
simple so that it is completely unambiguously how to do them. Examples
include operations such as adding, multiplying, or comparing two
numbers. Needless the say, the fewer steps the algorithm requires, the
better.

By exploiting quantum mechanics, a quantum computer introduces new basic
steps (like crossing the sea) that are impossible to perform on a
classical computer. In the previous chapter, we saw specific quantum
logic gates. Using these building blocks, we can formulate **quantum**
algorithms that might take fewer steps than the best classical algorithm
ever could!

### From algorithm to software

In the end, simply finding the 'recipe' itself is not enough: the
algorithm has to be turned into **software**, a piece of language that
tells a computer explicitly how to execute the step-by-step
instructions.

The difference between 'algorithms' and 'software' is subtle. An
algorithm is a purely mathematical description that describes precisely
how numbers should be manipulated. It could tell which two numbers must
be multiplied, what function must be evaluated, or how an image must be
adjusted. However, different computers can use different types of
processors and memory, and an algorithm does not describe how these
operations are done *on a specific computer.* This is where software
comes into play: it describes precisely what computer instructions must
be called, where each number is stored in memory, and how an image is
represented in binary.

As an analogy, you may think of the algorithm as a recipe to bake the
perfect chocolate cookie. The algorithm should unambiguously describe
what should happen to the ingredients: in what order they should be
mixed, how long they should be heated, etcetera. However, to build a
factory that produces these cookies, you need to be even more specific:
Where is the sugar stored? Out of what pipe does the dough flow? How are
cookies laid next to each other in the oven?

Fundamentally, core scientific breakthroughs come from finding new
algorithms. Once a new algorithm is found, it can be re-used many
different times on any capable machine (assuming a good software
developer will turn it into appropriate code!).

In this book, we care less about quantum software and more about quantum
algorithms. Firstly, the algorithms tell us precisely the functionality
that quantum computers can offer. Moreover, we don't yet know how a
mature quantum computer will be programmed or how quantum hardware and
software will change in the following years. On the other hand, the
knowledge of algorithms can be cherished forever.

Now that we have come to appreciate algorithms, it is natural to ask
*which* quantum algorithms we know of. What problems do quantum
computers solve well? And how to these algorithms compare to their
classical equivalents?

Further reading

-   [The Map of Quantum Computing
    (Youtube)](https://www.youtube.com/watch?v=-UlxHPIEVqA)  -- A
    30-minute video that forms a great supplement to this book. 

-   Chris Ferrie's book ['What You Shouldn\'t Know About Quantum
    Computers'](https://arxiv.org/abs/2405.15838)

-   Are you looking for a much more extensive source that covers pretty
    much everything there is to know about quantum computers? French
    consultant Olivier Ezratti maintains a 1300+ page book
    "[Understanding Quantum
    Technologies](https://www.oezratty.net/wordpress/2023/understanding-quantum-technologies-2023/)".

