---
layout: default
title: "Quantum hardware"
nav_order: 1
---

# Quantum hardware

Conventional computer hardware is extremely well standardized. No matter
what supplier you buy a computer from, you can be reasonably sure that
you can run your favourite applications on them. We expect to have
professional servers to run non-stop for years without the hardware ever
failing. Thanks to such high reliability and clear compatibility, it is
rather easy to compare different machines, by looking at speed (e.g.
floating-point operations per second, FLOPS) and memory size.

We will see that this is radically different for quantum computers:
devices make mistakes, have limited functionalities, and depending on
your application, you might like to use a completely different
architecture. In this chapter, we take a high-level business perspective
at quantum computing hardware. What should you know when starting your
quantum journey? 

## Different functionalities

The figure below shows different types of functionalities that quantum
computers can have (top, brown), along with some examples of hardware
that is available (below, yellow). This list is by no means complete! It
should at best give an impression of the current state of the art. Let
us start by taking a closer look at the functionalities.

<img src=" {{ site.baseurl }}/media/image22.png" style="width:6.26806in"
alt="universal simulator annealer 2023 1" />

Our biggest dream is to have a **‘universal quantum computer**’. The
word ‘universal’ indicates that it is capable of executing any quantum
algorithm (or technically: to approximate any algorithm’s output to
arbitrary precision). For comparison: your laptop, phone, and even a
smartwatch are universal classical computers, making them capable of
running any classical application you can think of: spreadsheets, 3D
games, data encryption, and so on. Similarly, a proper universal quantum
computer is suitable for any quantum application, regardless of whether
it is known today or invented in the future. 

The definition of ‘universal’ is blind to some details such as memory
limitations (it assumes you will never run out of RAM), and omits
tedious details about software compatibility (a Playstation game won’t
run on an XBox). In our high level overview, such details are
unimportant: the main point is that there also exist devices that
can *not *run just any algorithm.

**Does a universal computer need to be "gate-based"?**

No matter what architecture or qubit type you pick, our current
technology will not allow you to run very long computations. This is due
to the inherent imperfections in construction and control of quantum
devices. The imperfections cause errors to accumulate during a
computation, so that after some number of steps, the result is almost
surely corrupted and unusable. For longer computations, it is essential
to fix errors on the fly, using so-called **error correction** (also
known as: fault-tolerance).  

Today, we are stuck in a so-called NISQ-era, with **Noisy
Intermediate-Scale Quantum** devices. Many are in principle universal,
except that they are limited both in the number of qubits, *and* in the
number of steps that can be executed. Companies like IBM, IonQ,
Quantinuum and Pasqal all have NISQ computers available to test your own
programs on. 

Making a universal computer is challenging, and engineers can
make **special-purpose devices** that improve in certain areas (like
number of qubits or clock speed) by omitting certain functionalities. In
a **Quantum Simulator**, the computer specialises in simulating a
certain class of materials or molecules. The precise capabilities are
often captured in a Hamiltonian that specifies which materials qualify.
As an example, Harvard-spinoff QuEra has a quantum simulator available
over the cloud that mimics a quantum Ising model. Today’s simulators
(like QuEra’s) are fairly close to a universal computer (lacking only a
few technical ingredients) and are similarly subject to accumulating
errors. However, they are not designed to run conventional (gate-based)
algorithms.

There might be some confusion in jargon here, as the term ‘quantum
simulation’ is also sometimes used when a classical computer tries to
mimic the behaviour of a quantum computer. Others use the term
‘emulation’ for such classical approaches. 

See also:

- [QuEra announces a 256 qubit
  simulator](https://www.technologyreview.com/2021/11/17/1040243/quantum-computer-256-bit-startup/) available
  over the Cloud. 

- [Pasqal performs a material science simulation with 196
  qubits](https://www.pasqal.com/articles/simulating-phases-of-matter-in-magnetic-materials-with-qubits) and [sells
  100-qubit simulator in a EuroHPC
  tender](https://eurohpc-ju.europa.eu/two-100-qubits-quantum-computers-pasqal-fzj-and-genci-boost-hpcqs-pan-european-hybrid-hpcquantum-2022-05-30_en).

Another special-purpose device is the **Quantum Annealer, **for which
the Canadian scale-up D-Wave is especially well known. These
special-purpose devices can solve a certain class of optimization
problems that goes by the name
of [QUBO](https://en.wikipedia.org/wiki/Quadratic_unconstrained_binary_optimization):
quadratic unconstrained binary optimization. There is a well-developed
theory of mapping various problems into the QUBO formalism, making
annealers fairly versatile machines. However, quantum annealers will
never be able to take advantage of the various other quantum algorithms
out there: even with enough qubits, we don’t see them cracking codes
with Shor’s algorithm. 

See also:

- [D-Wave’s introduction to its quantum annealing
  platform](https://docs.dwavesys.com/docs/latest/c_gs_2.html)

##  Different building blocks

There is another question about what material the qubits are actually
made of. Scientists have cooked up several competing approaches, such as
superconducting materials, photons, or individual atoms, or ions, each
with their own strong and weak spots. The methodology or material used
to make a physical qubit is often called the qubit implementation, the
qubit type, or (we prefer) qubit **platform**. 

For conventional computer electronics, we converged to a single choice
of material and broadly a single manufacturing process, based on silicon
wafers and lithography. For quantum computers, there is still a fierce
race between the different platforms, and it is totally unclear which
will eventually be the winner — or whether we will converge to a single
winner at all. 

There is an interesting story behind the different hardware types, but
we won’t delve into that in this non-technical guide (would you
otherwise care what material your classical CPU is made of?). However,
anyone who wants to test quantum programs on actual hardware should
definitely know the details. Interested readers can start here:

***Further reading:***

- [Different types of qubits explained by
  Sifted.eu](https://sifted.eu/articles/quest-qubits-quantum-startups-explained)

- [Different types of qubits at IQC
  Waterloo](https://uwaterloo.ca/institute-for-quantum-computing/quantum-101/quantum-information-science-and-technology/what-qubit)

- [Different types of qubits on
  Wikipedia](https://en.wikipedia.org/wiki/Qubit#Physical_implementations)

- [A MOOC about different hardware types by TU
  Delft](https://online-learning.tudelft.nl/courses/the-hardware-of-a-quantum-computer)

It is interesting to note that all these different machines (universal,
annealers, simulators) can in principle be built using any type of
qubit. If you go back to the figure at the top, you can see that there
exist different qubit types with different functionalities. It’s not
unthinkable that the empty squares will also be filled, so that we have
access to superconducting-based simulators, or annealers that use
ultracold atom qubits (or perhaps the authors have missed this!). In
fact, we have already seen many academic showcases of superconducting
simulators
in [academic](https://arxiv.org/abs/2211.16439) [literature](https://www.nature.com/articles/ncomms8654).

TODO: ADD OVERVIEW TABLE OF WHAT SUPPLIERS HAVE.

