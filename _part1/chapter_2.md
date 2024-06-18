---
layout: default
title: 2 An introduction to the quantum world
nav_order: 2
---

## An introduction to the quantum world

![A magnifying glass over a circuit board Description automatically
generated](/media/image2.png){width="7.411615266841645in"
height="2.329364610673666in"}

<fieldset class="field-set" markdown="1"> 
<legend class="leg-title">At a glance</legend>

You don't need to understand quantum mechanics to understand the
*functionality* of quantum computers.

But if you insist: quantum mechanics describes the behaviour of the
smallest particles. It leads to many counter-intuitive phenomena:
computer memory can store multiple pieces of data at the same time, but
upon measurement, nature selects just a single piece (and throws away
all the others).

</fieldset>

If you want to drive a car, do you need to understand how its engine
works? Of course you don't! In a similar vein, you don't need to know
the details of quantum physics to read the rest of this book. So feel
free to skip this chapter.

Nevertheless, I know that most people *want* to have some conceptual
intuition about what quantum mechanics really is. It is not natural to
leave one of the most used word in this book as an abstract concept, and
it might be hard for the human brain to proceed without at least seeing
some examples.

Here is my best attempt to explain quantum mechanics in accessible
terms. Proceed with caution, as things will surely get confusing from
here.

### What is quantum?  

**Quantum physics** or **quantum mechanics** is the theory that
describes the tiniest particles, like electrons, atoms, and sometimes
even small molecules. They are the laws of nature that dictate cause and
effect at the scale of nanometers. You may contrast it to Newton's
classical physics, which works great for objects the size of a building
or football but becomes inaccurate at much smaller scales. Quantum is,
in a sense, a *refinement *of classical physics: the theories are
effectively identical when applied to a coffee mug, but one requires the
more difficult quantum theory to describe very small things. 

Some examples of systems where quantum could play a role are:

-   Atoms and the electrons that orbit around them.

-   Flows of electricity in microscopic (nano-scale) wires and chips

-   Photons, the particles out of which 'light' is made.

![A magnifying glass over a circuit board Description automatically
generated](/media/image3.png){width="6.267361111111111in"
height="0.65625in"}First, we need some physics jargon. The **state** of
the world is a complete description of everything there is to know about
its contents: all the particles inside it, their velocities, how much
they rotate, etcetera. Usually, the entire universe is too big to study,
so we often simplify our 'world' to just a single isolated particle, or
to a limited piece of computer memory. For example, for our prototypical
particle, we imagine we're only interested in its location, which we'll
call $x$ (and we forget about any other structure in the world). In the
spirit of computing, we might look at a 'bit' that stores information.
You may think of it as a tiny magnet that can either point 'up' (0) or
'down' (1). Note that a state is valid for just one instant, as there
could be reasons for it to change as time flows.

![](/media/image4.png){width="6.122641076115485in"
height="1.956583552055993in"}

### Four surprising phenomena in the quantum world

The most iconic quantum phenomenon is **superposition.** Think about any
property that we can (classically) measure, such as the position of a
particle, or the value of a bit on a hard drive (0 or 1). In quantum
mechanics, the state of the world can be such that several conflicting
measurement outcomes are 'true' at the same time: a particle can be at
multiple positions at once, or a bit could be 0 and 1 simultaneously.

How can you possibly describe a state like that? Well, if we look at
just a single particle, the state should contain a long list of all
possible positions: to what extent is it at position x=0, to what extent
at position x=1, and so forth, for every possible location that the
particle can be at. And indeed, this list could be infinite!

For the case of a bit, we'd need just two numbers denoting the extent to
which it is '0' or '1'. To make things even more confusing, these
numbers can be negative (and for math experts, they can even be complex
numbers). Because we will talk about quantum-mechanical bits a lot, we
will give them a shorter name: **qubits.** If we have a bunch of qubits
together, we'll call it a quantum memory.

To throw in some more examples, an electron can move at a velocity of 10
m/s and 100 m/s at the same time (which obviously also leads to a
superposition in its position). More relevant for us: a quantum memory
might use binary notation to store numbers 5 and 11 simultanously, or
even 46 different Microsoft Excel spreadsheets at once.

More physics-oriented books might call this the *particle-wave duality*:
all particles can also be described as a 'wave', which is yet another
description of how a particle is spread out over space. The wave is high
when a particle is very likely to be there, and small at unlikely
locations.

The second weird phenomenon is how **quantum measurements** work. Why do
we never observe an electron at two places at the same time? Why do I
never find my chair both moving and standing still? In quantum
mechanics, as soon as we measure the location of a particle, it
instantly jumps to just a single location at random. When we measure a
qubit, it jumps to either '0' or '1' with some probability. When we
measure the data in a quantum memory, we may find any one of the 46
spreadsheets that were stored.

This means that the world is intrinsically random (and hence, not
deterministic!). But this doesn't imply that we cannot understand it. We
can calculate the *probabilities* of measurement outcomes with
incredible precision as long as we know the state before the
measurement.

It is important to note that we cannot learn anything about the world
without measuring -- it is our only way to obtain data from the world,
and any process that extracts data must involve a measurement. However,
measurements are destructive in the sense that they change the state of
the world. In fact, they delete all the rich data encoded in a
superposition! If a particle was initially at position x=0, x=3 and
x=10, all simultaneously, then upon measurement, it jumps to one of
these three options. In jargon, we call this instantaneous change a
'collapse'. From then onwards, it is 100% at a fixed location: if we
measure x=3, then from then onwards, it is located uniquely at x=3 until
some other force starts acting on it. This means that, during a quantum
computation, we should be cautious about the timing of our measurements
-- we cannot just peek at the data at any moment we like, or we risk
disturbing a superposition.

Importantly, this also means that a single piece of quantum memory
cannot store an immense number of spreadsheets at the same time -- at
least, you wouldn't be able to retrieve each of them. To store 15 MB
worth of classical data, we need 15 MB worth of 'qubits'. Hence, quantum
computers are not particularly useful for storing classical data.

The fact that a 'measurement' changes the state of the world poses a
serious problem when engineering a quantum computer. No matter what
material we construct our qubits from, they will surely 'interact' with
other nearby particles, and some of these interactions could be
destructive measurements. We call this effect **decoherence**, and we
will later see that this forms one of the core challenges to building
large and accurate quantum computers.

At this point, quantum data doesn't seem particularly useful. Why would
we want to deal with superpositions if they lead to all this
uncertainty? Intuitively, think about the advantage of a quantum
computer in this way: what if we can jump between specific superposition
states to reach our goal (the correct answer) in very few steps,
exploiting states that a classical computer could never reach?

This is precisely what **quantum operations** do. These are physical
forces that change the state of a particle or a quantum memory. They can
turn a classical-looking state into a quantum superposition or vice
versa. They can act like logical operations, such as AND and OR, but
also like new quantum 'logic' that has no classical counterpart. Unlike
measurements, quantum operations are deterministic: they change quantum
states in a precisely defined way. In this book, we mainly deal with
operations that work on qubits. We will call such operations **quantum
gates** or simply 'gates'**.**

A quantum gate takes one or more qubits as input, changes their internal
state, and then outputs the same number of qubits (with their altered
states). In other words, the number of physical objects remains
unchanged, but their quantum states change. As an example, you may think
of our prototypical magnet that was initially pointing 'up', but a
quantum gate might flip this to 'down'. Because there are many possible
quantum gates, each having a different effect on their input, we like to
give them names in capital letters, such as [X, Z, H, and
CNOT](https://en.wikipedia.org/wiki/Quantum_logic_gate).

![](/media/image5.png){width="2.676101268591426in"
height="1.047169728783902in"}

In the same jargon as the 'quantum waves', we can see quantum operations
as manipulating these waves. This leads to effects similar to when you
throw two stones in a pond, and look at how the resulting waves meet:
when the peeks of two waves are at the same location, the water heights
will add up. We call this constructive interference. But waves can also
have 'negative' heights, where the water is lower than normal. Such
parts may cancel an incoming peak: destructive interference.\
Quantum gates will have similar effects on a qubit's quantum state, as
negative and positive property assignments can interfere destrictively
or constructively.

The canonical way to describe a quantum computer program is by defining
a sequence of quantum gates, one after the other, each of which could
act on a different set of qubits. At the end of the computation, we
measure all qubits. Below, an example of such a sequence is given, using
the standard Quantum Assembly (QASM) language.

![](/media/image6.png){width="4.4811318897637795in"
height="2.0817957130358704in"}

Together, these steps can be graphically displayed in a **quantum
circuit**, as shown here on the right. Quantum circuits represent each
qubit with a horizontal line and indicate time flowing from left to
right. Whenever a box with a letter is displayed over a qubit line, then
the corresponding gate should be applied. This isn't quite unlike the
way we read sheet music!

Note that when we run a circuit on an actual quantum computer, the final
measurements lead to probabilistic outcomes. We get to see a bunch of
ones and zeroes: one classical bit for each qubit. If the circuit was a
'good' quantum algorithm, then with high probability, these classical
bits will tell us the answer we were looking for. But even then, we
might need to redo the computation a few times and take (for example)
the most common result as our final answer.

If you are completely confused at this point, you are not alone. The
whole business of quantum superposition and quantum operations is
incredibly complex and is not something you could possibly master after
reading four pages. Even after studying the subject for many years, you
will encounter paradoxes and counter-intuitive phenomena. On the other
hand, I hope that the *functionality* of quantum circuits makes a lot of
sense: we define a list of instructions, and we employ machines that
execute these instructions in a well-defined way. This should be an
example of how we can operate a quantum device without understanding
what's going on under the hood.

There is one more quantum phenomenon to cover -- one that comes with a
mysterious flair around itself. We're talking about quantum
**entanglement.**

Imagine that we have two qubits, which we can transport independently
from each other without disturbing the data they store (in other words,
they remain in the same quantum state). According to quantum mechanics,
this pair of qubits may be simultaneously 00 and 11. Now, imagine that
computer scientist Alice grabs one of the qubits, takes it on her rocket
ship, and flies it all the way to dwarf planet Pluto. The other qubit
remains on Earth, in the hands of physicist Bob. Upon arriving on Pluto,
Alice measures her qubit and finds outcome '1'. A deep question is: what
do we now know about the other qubit?

Since the possible measurement outcomes were 00 and 11, the other can
only be measured as '1' from now onwards. It essentially collapses to be
100% in the state '1'. But how could the earth-based qubit possibly
*know* that a measurement occurred on Pluto? According to Einstein's
theory of relativity, information cannot travel faster than the speed of
light, which translates into a few hours between Earth and Pluto.
Nevertheless, measuring the qubit on earth will always give a consistent
result, even when done within the hour.

This paradox shows once again how confusing quantum mechanics can be.
However, the story above is perfectly consistent with both quantum
mechanics and relativity. The core principle is that *no information can
be sent faster than light between Alice and Bob*. For example, can you
see why Bob has no way of detecting when Alice reached Pluto just by
looking at his entangled qubit? In the most common interpretation of
quantum mechanics, the Earth qubit does indeed change its state
instantaneously when Alice measures, although there is no way to exploit
this effect.

There's a fascinating further discussion about the philosophy behind
entanglement, but we'll leave that to other sources. What matters to us
is that distant qubits can still share specific properties that would be
impossible classically, leading to new functionalities we can exploit.
We will discover what these functionalities are in the chapter on
quantum networks.

So there you have it: four surprising phenomena you may hear frequently
in quantum technology conversations. To summarise:

-   Superposition: the phenomenon where a qubit is both 0 and 1 at the
    same time.

-   Quantum measurement: measuring a quantum memory destroys
    superposition. The result we obtain is probabilistic.

-   Quantum operations/gates: deterministic changes to the state of
    qubits, which generalise classical logic gates like OR, AND, NOT. A
    list of several quantum gates forms a quantum circuit.

-   Entanglement: Qubits separated over a long distance can still share
    unique properties.

If you'd like to know more about the physics and math behind qubits, we
recommend the following sources:

-   [Quantum Country](http://new.quantum.country/) -- a great online
    textbook about Quantum Computing by Andy Matuschak and Michael
    Nielsen.

-   [QuTech Academy's ](https://www.qutube.nl/)*[School of
    Quantum]{.underline} -- *A broad range of topics explained using
    short videos. 

