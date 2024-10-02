---
layout: default
title: "An introduction to the quantum world"
nav_order: 2
---
 
 
# An introduction to the quantum world
{: .no_toc }


Reading time: 17 minutes
{: .fs-3 .floatr }

### Contents
{: .no_toc }
{: .mini-header } 

- TOC
{:toc}




<fieldset class="field-set" markdown="1"> 
<legend class="leg-title mini-header">At a glance</legend>

You don’t need to understand quantum mechanics to understand the
*functionality* of quantum computers.

But if you insist, quantum mechanics describes the behaviour of the
smallest particles. It leads to many counter-intuitive phenomena:
computer memory can store multiple pieces of data at the same time, but
upon measurement, nature selects just a single piece (and throws away
all the others).

</fieldset> 
 <hr> 

If you want to drive a car, do you need to understand how its engine
works? Of course, you don’t! In a similar vein, you don’t need to know
the details of quantum physics to read the rest of this book. So feel
free to skip this chapter.

Nevertheless, I know that most people *want* to have some conceptual
intuition about what quantum mechanics really is. It is not natural to
leave one of the most used words in this book as an abstract concept,
and it might be hard for the human brain to proceed without at least
seeing some examples.

Here is my best attempt to explain quantum mechanics in accessible
terms. Proceed with caution, as things will surely get confusing from
here.

## What is quantum?  

**Quantum physics** or **quantum mechanics** is the theory that
describes the tiniest particles, like electrons, atoms, and small
molecules. The theory is meant to describe the fundamental laws of
nature using a set of mathematical equations, allowing us to predict
cause and effect at the scale of nanometers. It answers questions like
‘What happens when I bring two electrons close together?’ or ‘Will these
two substances undergo a chemical reaction?’. You may contrast quantum
mechanics to Newton’s classical physics that we learned in high school,
which works great for objects the size of a building or football but
becomes inaccurate at much smaller scales. Quantum is, in a sense,
a *refinement *of classical physics: the theories are effectively
identical when applied to a coffee mug, but the more difficult quantum
theory is needed to describe very small things. 

Some examples of systems where quantum could play a role are:

- Atoms and the electrons that orbit around them.

- Flows of electricity in microscopic (nano-scale) wires and chips.

- Photons, the particles out of which light is made.

To proceed, we need some physics jargon. We like to use the word
‘**state**’, which is a complete description of all the physical
properties of the world at one instance: the locations of all the
different particles, their velocities, how much they rotate, etcetera.
Usually, the entire universe is too big to study, so we often simplify
our world to just a single isolated particle or to a limited piece of
computer memory. Let’s imagine a bare particle in an otherwise empty
world. We may be interested in its location, which we’ll call \\(x\\). For
example, the world might look something like the image below, which can
be described by a very simple state: \\(x = 5\\) (the ruler is just
virtual).

<img src=" {{ site.baseurl }}/media/image2.png" style="width:2.8in" />

In the spirit of computing, we might look at a ‘bit’ that stores
information. You may think of it as a tiny magnet that can either point
‘up’ (1) or ‘down’ (0). The state of a piece of memory is easy to
describe, simply by stating the bit values one by one. For example:
11010.

<img src=" {{ site.baseurl }}/media/image3.png"
style="width:2.53184in" />

Importantly, the state of the world can change over time. We will often
care about the state of the world at a certain moment, for example, at
the beginning of computation or at the end of it.

## Four surprising phenomena

The most iconic quantum phenomenon is **superposition.** Think about any
property that we can (classically) measure, such as the position of a
particle or the value of a bit on a hard drive (0 or 1). In quantum
mechanics, the state of the world can be such that many different
measurement outcomes are somewhat ‘true’ at the same time: a particle
can be at multiple positions at once, or a bit could be 0 and 1
simultaneously. When we say ‘at the same time’ we mean that, to predict
any cause and effect, we need to keep track of all these possibilities.
To illustrate, I sometimes picture a quantum particle to split into many
opaque copies of itself, spread out over space, where the degree of
transparency determines how likely the particle is to be found there:
the darker, the more likely.

<img src=" {{ site.baseurl }}/media/image4.png"
style="width:4.91228in" />

How can you possibly describe a state like that? For a single particle,
the state is a long list, where for each possible position, we store a
number called the *amplitude,* which is related to how likely the
particle is to be found at that location. In other words, the state
describes precisely to what extent a particle is at position \\(x = 0\\), to
what extent at position \\(x = 1\\), and so forth, for every possible
location that the particle can be at. And indeed, this list could be
infinitely long! Luckily, when dealing with computers, we work with
simpler objects. A quantum bit needs just two amplitudes, which denote
the extent to which the bit is ‘0’ or ‘1’, respectively. Because we will
talk about quantum-mechanical bits a lot, we will give them a shorter
name: **qubits.** If we have a bunch of qubits together, we’ll call it a
quantum memory.

To throw in some more examples of weird quantum states, an electron can
move at a velocity of 10 m/s and 100 m/s at the same time (which
obviously also leads to a superposition in its location). More relevant
for us: a quantum memory might store the numbers 5 and 11
‘simultaneously’ or even 46 different Microsoft Excel spreadsheets ‘at
once’.

These amplitudes feel somewhat analogous to probabilities, which can
similarly describe the likelihood that a particle can be found at some
location. However, there is a fundamental difference. Probabilities in
the classical world help us deal with information we don’t have: surely,
the particle is already at some location, but perhaps we just don’t know
which location yet. Quantum mechanics is different. Even if we know
every tiny detail about the location of a particle, we still need to
describe it as a superposition. Fundamentally, the location is *not
determined* yet. Hence, there is literally no better way to describe the
particle than by tracking this convoluted superposition. Amplitudes are
also more finicky to deal with than probabilities because these numbers
can become negative (and for math experts, they can even be complex
numbers).

The second weird phenomenon is how **quantum measurements** work. Why do
we never observe an electron at two places at the same time? Why do I
never find a car both moving and standing still? In quantum mechanics,
as soon as we measure the location of a particle, it instantly jumps to
just a single location at random – making its location fully determined.
Similarly, when we measure a qubit, it jumps to either ‘0’ or ‘1’. When
we measure the data in a quantum memory, we may find any one of the 46
spreadsheets that were stored.

This means that our world is intrinsically random (and hence, not
deterministic!). But this doesn’t imply that we cannot understand it. We
can calculate the *probabilities* of measurement outcomes with
incredible precision as long as we know the state before the
measurement.

It is important to note that we cannot learn anything about the world
without measuring – it is our only way to obtain data from the world.
Any observation, even a slight peek at our system, is a measurement in
quantum mechanics. However, measurements are destructive in the sense
that they change the state of the world. We fundamentally cannot ‘look’
at a particle without disturbing it. In fact, they delete all the rich
data encoded in a superposition! If a particle was initially at position
\\(x = 0\\),\\(\ x = 3\ \\)and \\(x = 10,\\) all simultaneously, then upon
measurement, it jumps to one of these three options. In jargon, we call
this instantaneous change a ‘collapse’. From then onwards, it is 100% at
a fixed location: if, at first, we measure the particle to be at
\\(x = 3\\), then any subsequent measurement will give the same result,
until some other force moves it again. This means that, during a quantum
computation, we should carefully choose when we perform any measurements
– we cannot just peek at the data at any moment we like, or we risk
disturbing a superposition.

This also means that a single piece of quantum memory cannot store an
immense number of spreadsheets at the same time – at least, you wouldn’t
be able to retrieve each of them. To store 15 MB worth of classical
data, we need 15 MB worth of qubits. Hence, quantum computers are not
particularly useful for storing classical data.

The fact that a measurement changes the state of the world poses a
serious problem for the engineers who are building quantum computers. No
matter what material we construct our qubits from, they will surely
interact with other nearby particles, and some of these interactions
could act like destructive measurements. We call this effect
**decoherence**, and we will later see that this forms one of the core
challenges to large-scale quantum computation.

At this point, quantum data doesn’t seem particularly useful. Why would
we want to deal with superpositions if they lead to all this
uncertainty? Intuitively, think about the advantage of a quantum
computer in the following way. Using quantum mechanics, a device can
manipulate data in ways that a classical computer could never do.

A quantum computer can manipulate the data it stores using so-called
**quantum gates**, or simply ‘gates’ for short. These are rapid bursts
of some physical forces that change the state of one or more qubits.
They can turn a classical-looking state into a quantum superposition or
vice versa. They can act like logical operations, like the AND and OR
gates that are used in classical electronics, but also like new quantum
logic that has no classical counterpart.

From a functional perspective, a quantum gate takes one or more qubits
as input, changes their internal state, and then outputs the same number
of qubits (with their altered states). In other words, the number of
physical objects remains unchanged, but the overall state changes. As an
example, you may think of our prototypical magnet that was initially
pointing ‘up’, but a quantum gate might flip this to ‘down’. There are
many such gates possible, each having a different effect on their input.
We like to give them names in capital letters, such as [X, Z, H, and
CX](https://en.wikipedia.org/wiki/Quantum_logic_gate). Importantly, a
quantum gate is *deterministic,* meaning that its input-output behaviour
is always the same, as opposed to the quantum measurements we saw
earlier.

<img src=" {{ site.baseurl }}/media/image5.png" style="width:2.2748in" />

The canonical way to describe a quantum computer program is by defining
a sequence of quantum gates, where for each gate, we also indicate what
qubits are supposed to be the gate’s input. At the end of the
computation, we measure all qubits. Below, an example of such a list is
given, using the standard Quantum Assembly (QASM) language.

<img src=" {{ site.baseurl }}/media/image6.png"
style="width:6.26806in" />

Together, these steps can be graphically displayed in a **quantum
circuit**, as shown here on the right. Quantum circuits represent each
qubit with a horizontal line and indicate time flowing from left to
right. Whenever a box with a letter is displayed over a qubit line, then
the corresponding gate should be applied. This isn’t unlike the way we
read sheet music! You may notice that sometimes, two or more gates can
be performed in parallel as long as they act on different qubits.

When we run a circuit on an actual quantum computer, the final
measurements lead to probabilistic outcomes. We get to see a bunch of
ones and zeroes: one classical bit for each qubit. If the circuit was a
good quantum algorithm, then with high probability, these classical bits
will tell us the answer we were looking for. But even then, we might
need to redo the computation a few times and take (for example) the most
common result as our final answer.

If you are completely confused at this point, you are not alone. The
whole business of quantum superposition and quantum operations is
incredibly complex and is not something you could possibly master after
reading a few pages. Scientists who have studied the subject for many
years are still frequently baffled by deceptive paradoxes and
counter-intuitive phenomena. On the other hand, I hope that the
*functionality* of quantum circuits makes some sense: we define a list
of instructions and feed them into a machine that can execute them. We
don’t have to know precisely what’s going on under the hood!

There is one remaining quantum phenomenon to cover – one that comes with
a mysterious flair surrounding it. We’re talking about quantum
**entanglement**, which we’ll describe using the following example.

Imagine that we have two qubits, which we can transport independently
from each other without disturbing the data they store. Together, the
bits can represent the states 00, 01, 10 or 11, or any superposition of
these. According to quantum mechanics, we can create a very specific
state where the pair of qubits is simultaneously 00 and 11. Now, imagine
that computer scientist Alice grabs one of the qubits, takes it on her
rocket ship, and flies it all the way to dwarf planet Pluto. The other
qubit remains on Earth in the hands of physicist Bob. Upon arriving on
Pluto, Alice measures her qubit and finds outcome ‘1’. A deep question
is: what do we now know about Bob’s qubit?

Since the only possible measurement outcomes were 00 and 11, the other
qubit can only be measured as ‘1’ from now onwards. It essentially
collapses to be 100% in the state ‘1’. But how could the earth-based
qubit possibly *know* that a measurement occurred on Pluto? What
mechanism made it collapse? According to Einstein’s theory of
relativity, information cannot travel faster than the speed of light,
which translates into a few hours between Earth and Pluto. Nevertheless,
measuring the qubits in two faraway locations will always give a
consistent result, even when the two qubits are measured at exactly the
same time.

This paradox shows once again how confusing quantum mechanics can be.
However, the story above is perfectly consistent with both quantum
mechanics and the theory of relativity. The core principle is that *no
information can be sent faster than light between Alice and Bob*. For
example, can you see why Bob has no way of detecting when Alice performs
her measurement just by looking at his entangled qubit? In the most
common interpretation of quantum mechanics, the Earth qubit does indeed
change its state instantaneously when Alice measures, although there is
no way to exploit this effect.

There’s a fascinating further discussion about the philosophy behind
entanglement, but we’ll leave that to other sources. What matters to us
is that distant qubits can share specific properties that would be
impossible to mimic classically, leading to new functionalities we can
exploit. We will discover what these functionalities are in the chapter
on [quantum
networks](https://quantumcomputingforbusiness.com/applications/networks/).

So there you have it: four surprising phenomena you may hear frequently
in quantum technology conversations. To summarise:

- Superposition: the phenomenon where a qubit is both 0 and 1 at the
  same time.

- Quantum measurement: measuring a quantum memory destroys
  superposition. The result we obtain is probabilistic.

- Quantum gates: deterministic changes to the state of qubits, which
  generalise classical logic gates like OR, AND, NOT. A list of several
  quantum gates (together with the qubits they act on) forms a quantum
  circuit.

- Entanglement: Qubits separated over a long distance can still share
  unique properties.

## What does a quantum computer look like?

Most large-scale computing today happens in data centres, where we don’t
care much about the specifics of the devices that do our calculations.
We also expect that future quantum computers will mostly be tucked away
in the ‘cloud’, making their appearance and inner workings largely
irrelevant to most users. However, for this optional chapter, we can
take the opportunity to view what today’s cutting-edge hardware looks
like. There are many different ways to build a quantum computer, each
working in vastly different ways. Here, we describe the example of
so-called superconducting qubits, a relatively mature platform used by
companies like IBM, Google and Rigetti and several academic institutes.
Research institute QuTech in Delft, The Netherlands, was so kind to
provide photos that allow us to look inside their labs. We will see that
only a tiny part of the computer is actually ‘quantum’, whereas most of
the machine consists of bulky classical machinery that’s required to
keep the computer working.

<img src=" {{ site.baseurl }}/media/image7.png"
style="width:6.32428in" />

{: .caption }  
A quantum chip. Photo credits: Marc Blommaert for QuTech.

The real quantum magic happens on a chip, not unlike the computer chips
used in your laptop or phone. The qubits are formed by tiny electronic
circuits where the flow of electrical current is restricted to just one
out of two states: the ‘bit’ states 0 and 1. Since this is a quantum
system, the current can also be in a superposition – picture all the
electrons in the wire participating both in flow ‘0’ and flow ‘1’
simultaneously! This only works when the chip is cooled down to
unimaginably low temperatures, down to around 10 milliKelvin – a
hundredth of a degree above absolute zero. At these temperatures, the
electronic circuits become superconducting, such that an initial current
can flow indefinitely. This is important because any damping of the
current would cause unwanted disturbance to the qubit state.

The temperature constraint is why the quantum chip is placed in a
massive dilution refrigerator, a cylinder of about half a meter in
diameter and over a meter tall, which specialises in keeping the quantum
chip cool. In the future, larger quantum computers may need even bigger
fridges or have several of these close together. Deeper parts of the
fridge have different temperatures, allowing us to cool in stages. An
example could be to cool a first environment to 35 Kelvin (-283 °Celsius
or -396.7 °Fahrenheit), followed by subsequent stages to ~3K, 900mK,
100mK, until the final stage of ~10mK is reached.

<img src=" {{ site.baseurl }}/media/image8.png" style="width:5.3427in" />

{: .caption }  
The interior of a dilution fridge, as used for superconducting quantum
computers. Photo credits: Marc Blommaert for QuTech.

Engineers typically suspend the fridge on the ceiling so that the higher
temperatures are on top, and the ultracold quantum chip is placed at the
very bottom. The internals are shaped accordingly: several layers of
gold disks are suspended below one another, one disk for each
temperature zone. A large number of wires run between the disks,
transporting signals between the ceiling and the lowermost areas. The
whole structure forms the iconic metal chandelier that you often see in
images, although it would all be covered by a boring metal case when the
fridge is in operation.

To make the qubits do something useful, like executing a quantum gate or
performing a measurement, we need to send signals into the chip. Just
like in classical computers, these signals are technically voltage
differences between various wires. Some voltages remain constant over
time, others oscillate at microwave frequencies. The wiring itself
becomes increasingly challenging for larger quantum computers for two
reasons. Firstly, we currently need around 2-4 wires to control a single
qubit, which is problematic when we scale to millions of qubits – it’s
impossible to connect that many wires to a tiny chip. We’ll need to find
‘multiplexing’ solutions, where a single wire can serve multiple qubits
at once. Secondly, many wires connect the ultracold chip to other
hardware that sits at room temperature, forming a channel for heat and
noise to enter. The dilution fridge circumvents this by incrementally
cooling and damping the signals as they travel through the different
layers of the fridge, but it can only handle so many cables.

<img src=" {{ site.baseurl }}/media/image9.png"
style="width:5.98904in" />

{: .caption }  
A stack of classical control electronics used to generate and measure
electronic signals. Photo credits: Marc Blommaert for QuTech.

Besides the large chandelier, an array of specialised control
electronics is needed to produce the necessary electronic pulses and to
carefully read out the tiny signals that qubits produce when we measure
them. These devices sit in one or multiple electronics racks, each half
a meter wide and nearly two meters tall, similar to the ones you’ll find
in a typical data centre. Ironically, the actual quantum software can be
written on a simple laptop, from where the instructions are passed to
the control electronics to run a quantum circuit.

The whole situation is reminiscent of computers in the 1940s and 1950s,
which similarly occupied a large room and required several engineers for
all kinds of laborious manual maintenance tasks. On top of this, the
dilution fridges are particularly noisy – to the extent that those who
operate them ideally do this from a different room – and are fairly
power-hungry. The quantum computer described above consumes around 25
kW, comparable to driving an electric car.

To summarise, a quantum computer based on superconducting qubits
consists mostly of bulky classical stuff: a large cylindrical fridge and
a rack full of classical electronic devices, all of which work together
to keep the microscopic qubits in the coldest part of the fridge
working.

## Further reading

If you’d like to know more about the physics and math behind qubits, we
recommend the following sources:

- [Quantum Country ](http://quantum.country/)– a great online textbook
  about Quantum Computing by Andy Matuschak and Michael Nielsen.

- [QuTech Academy’s School of
  Quantum](https://www.qutube.nl/)* *explains a broad range of quantum
  topics using short videos. 

- (Youtube) [A video tour that looks inside IBM’s superconducting
  quantum computer](https://www.youtube.com/watch?v=4gpPHWCoWPs).

