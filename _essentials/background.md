---
layout: default
title: "The background: why are we so enthusiastic about quantum?"
nav_order: 3
---

# The background: why are we so enthusiastic about Quantum Technology? 

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

## What is quantum technology?

Quantum physics has already proven itself as an invaluable basis for
technologies such as LED lighting, MRI scanners and solar cells. And
it’s still relevant to push the limits of innovation, with [nano-cars
that consist of just a few
atoms](https://www.rug.nl/news/2019/12/molecular-motors-and-switches?lang=en),
or [ever-smaller transistors on computer
chips](https://www.nature.com/articles/nature.2012.9747) on the horizon.

Just ahead of us is a new paradigm, which we’ll call quantum technology.
The distinguishing factor is that it goes further than merely building
stuff from small particles. Quantum technology is about devices that
perform certain processes in a fundamentally different way. That is, the
data (or operations) we work with can have special properties unique to
quantum physics, such as superposition and entanglement.

In our jargon, we will refer to ‘classical’ technology for devices that
don’t carefully exploit the possibilities of quantum physics – they are
based on ‘classical’ physics that we’re used to from high school. Your
laptop and phone are examples of classical computers, and they’re
connected to the classical internet. The internal transistors and
electrical circuits might be so tiny that quantum physics is relevant
there, but the fundamental point is that the information that they
process is purely classical. Whereas classical computers work with
‘bits’, quantum technology will store information in something called
‘quantum bits’, or shortly ‘qubits’. Generally, under the nomer
of **quantum technology**, we distinguish four categories:

{{ begin comparison table }}

Quantum Computers

Quantum computers are devices that use quantum physics to perform
automatic calculations to solve a problem. Computing is considered the
most impactful application for most organisations, and therefore, it’s
the main focus of this book. 

Quantum Networks

Quantum networks are connections between quantum devices over
which *qubits* (or similar forms of quantum data)* *can be transmitted.
The most relevant use case is to strengthen cryptography used by
classical computers, but there are many more applications.

Quantum Sensors

Quantum sensors are devices that exploit the effects of quantum physics
to accurately measure certain quantities, such as a magnetic field or
the strength of the earth’s gravity. Quantum clocks also fall into this
category. 

Quantum Simulators

Quantum simulators are devices similar to quantum computers, except that
they specialise in solving a limited set of problems. Typically, they
are built to reproduce the behaviour of atoms and electrons in a
molecule or a piece of material, allowing us to measure properties like
energies and reaction rates.

{{ end comparison table }}

In this book, we mainly focus on **computers **and **networks**: simply
because these seem to have the biggest impact on typical (business)
users.

## 

## The importance of high-performance computing

The abundance of cheap computational power has given humanity incredible
wealth. We automated the most tedious tasks to free up time for leisure
and to solve other urgent problems. It allowed us to scale factories,
supply chains and logistics to unprecedented sizes, allowing us to
transport resources around the globe at minimal costs. Computer chips,
aeroplane wings, heart monitors, and LCD screens have improved with
every generation.

Today, our computers are already incredibly fast. In fact, for many
applications, there is little economic gain in making these computers
even faster. Decades-old machines can successfully oversee factory
operations, and writing a Word document or scheduling a meeting with 8
busy colleagues is not limited by faster computers in any way.

However, this book specifically is about the applications where we are
still hungry for more computational power. If only we could feed more
data into weather models, our forecasts would become more accurate. If
staff rostering would take less time, we could take better take
last-minute changes into account. Accurate predictions of drug
reactivity in a human body could save on costly medical trials and
reduce the time to market. Machine learning models like ChatGPT are
still demanding more training hours to produce more sophisticated
results.

It should be clear that we’re not talking about computations that happen
on your laptop. We’re thinking of problems where somehow there’s value
in investing in the fastest possible computers on earth:
**high-performance computing (HPC)**, colloquially called
*supercomputers***.** Merely looking at the market, there seems to be
incredible value computing stuff: companies and academics spend tens of
billions of dollars on them[^2], and Nvidia recently became the most
valuable company on earth by leading the market of special purpose
Graphical Processing Units (GPU’s).

[^2]: See e.g.
    <https://www.marketsandmarkets.com/Market-Reports/Quantum-High-Performance-Computing-Market-631.html>
    and
    <https://www.mordorintelligence.com/industry-reports/cloud-high-performance-computing-hpc-market>

## 

## Why can quantum computers have an advantage? 

Quantum computers are devices that perform automatic computations at our
command, very much like their classical counterparts. The ‘quantum’ part
stems from the fact that it can actually exploit the laws of quantum
mechanics. This should be contrasted to our conventional ‘classical’
computers, which technically can also be completely described by quantum
mechanics, but they just happen to also work fine according to classical
physics. By no means are they supposed to ever deal with quantum
phenomena
like [superposition](https://en.wikipedia.org/wiki/Quantum_superposition) or [entanglement](https://en.wikipedia.org/wiki/Quantum_entanglement).
Contrarily, a proper quantum computer does exploit these purely quantum
mechanical effects. 

A naive view of quantum computers is that they’re simply *faster* than
their conventional cousins. Or perhaps one may naively point at Moore’s
Law: with transistors reaching atomic scales, we run into quantum
effects, so quantum physics may help us make better chips. However, none
of these are our core motivations for looking at quantum computers. 

Firstly, **quantum computers are much, much slower than conventional
computers,** if one focuses on their ‘time to perform a basic step’. A
modern CPU can handle 64-bit numbers (meaning that arbitrary numbers up
to 18,446,744,073,709,551,615 (!) can be processed). It can perform
basic arithmetic like addition, multiplication, and so forth on these
numbers, essentially in one single ‘step’. The speed of a modern CPU is
incredible: a modern Intel or AMD processor works at a rate of several
GHz, that is, several billions of steps per second. There’s no way a
human can possibly keep up with such speeds when it comes to plain
calculations! 

Now, quantum computers are supposed to be even faster, right? Well, it’s
not hard to find backing for that claim: 

<img src=" {{ site.baseurl }}/media/image8.png"
style="width:4.44635in" />

<img src=" {{ site.baseurl }}/media/image9.png"
style="width:5.06565in" />

However, you may be disappointed to hear that quantum computers, at this
moment, cannot even add or multiply numbers of more than 3 or 4 bits.
And even if they could, their rate of operation would by no means reach
several GHz, but more likely several MHz (a few *million* operations per
second), at best. In other words, they’re more than a thousand
times *slower. *To make things worse, the information in quantum
computers is extremely fragile and needs to be constantly checked and
corrected, using so-called **error correction***. *This is a form of
overhead that could make quantum computers another several orders of
magnitude slower. Even in the far future, when quantum computers are
more mature and more reliable, we still expect them to be much slower
than the classical chips at that time. 

How does this rhyme with the news about ever-faster quantum computers?
And why are we still interested in these slow machines? As we claimed
before, we hope to do certain computations in a **fundamentally
different way**. Let’s look at a beautiful analogy that Andy Matuschak
and Michael Nielsen bring up in their online course
[Quantum.country](https://quantum.country/). 

<img src=" {{ site.baseurl }}/media/image10.jpeg"
style="width:3.86142in" />

Imagine that you’d like to travel from Morocco to Spain. If your
technology does not allow you to cross the Strait of Gibraltar (say, you
have access to a car but not a boat), then you’d need to take an
incredible detour: all the way through North Africa, past the Arabian
Peninsula, and through Europe, before you can reach your destination.
This represents the steps taken by a classical computer. In the same
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
greatly from a quantum computer, whereas many won’t: you would not want
to travel by hovercraft from Amsterdam to Berlin. For this reason, we
don’t expect that classical computers will be ‘replaced’ any time soon.
Instead, different types of processors (CPUs, GPUs, quantum computers)
are expected to co-exist. GPU and Quantum Processing Units (QPUs) are
special-purpose devices, meant to only do tricks that they happen to be
good at.

In the analogy with the Strait of Gibraltar, the precise route that you
travel denotes the chosen **algorithm**. An algorithm is a step-by-step
list of instructions that describes how a computational problem should
be solved. The ‘steps’* *here should be sufficiently simple so that it
is completely unambiguously how to do them. They could be operations
such as adding, multiplying, or comparing two numbers. Needless the say,
the fewer steps the algorithm requires, the better.

By exploiting quantum mechanics, a quantum computer introduces new basic
steps (like crossing the sea) that are impossible to perform on a
classical computer. For example, the previous chapter introduced quantum
logic gates that generalise operations like AND and OR. Using these
building blocks, we can formulate quantum algorithms that might take
fewer steps than the best classical algorithm ever could!

A recurring theme in this book is the search for quantum algorithms with
a significant advantage over their classical counterparts. This turns
out to be more challenging than it seems at first sight: the algorithm
must have a significant advantage to compensate for the ‘slowness’ of
the quantum computer, and the number of algorithms that accomplish this
is still quite small. We might go as far as to say that, even if we had
a large-scale quantum computer today, its value would be limited. For
this reason, the ongoing development of novel algorithms is incredibly
important.

## From algorithm to software

In the end, simply finding the ‘recipe’ itself is not enough: the
algorithm has to be turned into **software**, a piece of language that
tells a computer explicitly how to execute the step-by-step
instructions.

The difference between ‘algorithms’ and ‘software’ is subtle. An
algorithm is a purely mathematical description that describes precisely
how numbers should be manipulated. It could tell which two numbers must
be multiplied, what function must be evaluated, or how an image must be
transformed. However, different computers can use different types of
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
that quantum computers can offer. Moreover, we don’t yet know how a
mature quantum computer will be programmed or how quantum hardware and
software will change in the following years. On the other hand, newfound
algorithms can be cherished forever.

Now that we have come to appreciate algorithms, it is natural to ask
*which* quantum algorithms we know of. What problems do quantum
computers solve well? And how do these algorithms compare to their
classical equivalents? This will be the topic of the next chapter.

## Further reading

- [The Map of Quantum Computing
  (Youtube)](https://www.youtube.com/watch?v=-UlxHPIEVqA)  – A 30-minute
  video that forms a great supplement to this book. 

- Chris Ferrie’s book [‘What You Shouldn't Know About Quantum
  Computers’](https://arxiv.org/abs/2405.15838) debunks several myths
  about quantum computers, presented in a very accessible way.

- Are you looking for a much more extensive source that covers pretty
  much everything there is to know about quantum computers? French
  consultant Olivier Ezratti maintains a 1300+ page book “[Understanding
  Quantum
  Technologies](https://www.oezratty.net/wordpress/2023/understanding-quantum-technologies-2023/)”.

