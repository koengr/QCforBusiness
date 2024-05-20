---
layout: default
title:  "The background"
date:   2024-05-20 15:15:41 +0200
categories: guide
theme: just-the-docs
nav_order: 2

---

* This will become a table of contents (this text will be scrapped).
{:toc}

## The background: why are we so enthusiastic about Quantum Technology?

### What is Quantum?

**Quantum Physics**  is the theory that describes the smallest particles, like electrons, atoms, and sometimes even small molecules. It's the machinery that describes things that happen at the scale of nanometers. You may contrast it to Newton's classical physics, which works great for objects that are the size of a human, but becomes inaccurate at much smaller scales. Quantum is, in a sense, a _refinement _of classical physics: the theories agree for large objects, but one requires the more difficult quantum theory to describe small things.

It should not come as a surprise that quantum physics is relevant for several kinds of technology that operate on a small scale, like [nano-cars that consist of just a few atoms](https://www.rug.nl/news/2019/12/molecular-motors-and-switches?lang=en), or [ever-smaller transistors on computer chips](https://www.nature.com/articles/nature.2012.9747). However, quantum technology goes further than simply telling us how to handle small particles:  **quantum allows us to perform certain processes in a fundamentally different way. ** We will see an insightful example of this very soon.

In particular, we will refer to 'classical' technology to mean devices that don't carefully exploit the possibilities of quantum physics. For example, you're most likely reading this on a classical computer or phone right now, using the classical internet. Whereas classical computers work with 'bits', quantum technology will store information in something called 'quantum bits', or shortly 'qubits'. Generally, under the nomer of  **quantum technology**, we distinguish four categories:

--- Begin fancy comparison table:

Quantum Computers

Devices that use quantum physics to perform automatic calculations in order to solve a certain problem. Computing is the main focus of this blog.

Quantum Networks

A connection between quantum devices over which _qubits _can be transmitted. The most relevant use case is to strengthen cryptography used by classical computers, but there are many more applications.

Quantum Sensors

Devices that exploit quantum-mechanical effects to accurately measure certain quantities, like a magnetic field or the strength of the earth's gravity. Quantum clocks also fall in this category.

Quantum Simulators

Devices that carefully reproduce the behaviour of atoms and electrons in a piece of material, allowing us to understand the properties of said material.

--- End comparison table

In this blog, we mainly focus on  **computers ** and  **internet**: simply because these will have the biggest impact on typical (business) users. If you'd like to know more about the technical details, we recommend the following sources as a great introduction:

- [Quantum Country](http://new.quantum.country/) – a great online textbook about Quantum Computing by Andy Matuschak and Michael Nielsen.
- [QuTech Academy's ](https://www.qutube.nl/)_School of Quantum__ – _A broad range of topics explained using short videos.
- [The Map of Quantum Computing (Youtube)](https://www.youtube.com/watch?v=-UlxHPIEVqA)  – A 30-minute video that forms a great supplement to this blog.

### What can Quantum Technologies do for us?

Quantum computers are devices that perform automatic computations at our command, very much like their classical counterparts. The 'quantum' part stems from the fact that it can actually exploit the laws of quantum mechanics. This should be contrasted to our conventional 'classical' computers, which technically can also be completely described by quantum mechanics, but they just happen to also work fine according to classical physics. By no means are they supposed to ever deal with quantum phenomena like [superposition](https://en.wikipedia.org/wiki/Quantum_superposition) or [entanglement](https://en.wikipedia.org/wiki/Quantum_entanglement). Contrarily, a proper quantum computer does exploit these purely quantum mechanical effects.

A naive view of quantum computers is that they're simply _faster_ than their conventional cousins. Or perhaps one may naively point at Moore's Law: with transistors reaching atomic scales, we run into quantum effects, hence quantum physics may help us make better chips. However, none of these are our core motivation to look at quantum computers.

Firstly,  **quantum computers are much, much slower than conventional computers,**  if one focuses on their 'time to perform a basic step'. A modern CPU can handle 64-bit numbers (meaning that all numbers between 0 and 264-1= 18,446,744,073,709,551,615 can be represented). It can perform basic arithmetic like addition, multiplication, and so forth on these numbers, essentially in one single 'step'. The speed of a modern CPU is incredible: a typical Intel or AMD processor bought in 2022 performs these steps at roughly 4 GHz , i.e., 4 billion steps per second. There's no way a human can possibly keep up with such speeds when it comes to plain calculations!

Now, quantum computers are supposed to be even faster, right? Well, it's not hard to find backing for that claim:

- [Google creates quantum chip millions of times faster than the fastest supercomputer](https://www.techradar.com/news/google-creates-quantum-chip-millions-of-times-faster-than-the-fastest-supercomputer)
- [Chinese Scientists Create Quantum Processor 60,000 Times Faster Than Current Supercomputers](https://www.iflscience.com/technology/chinese-scientists-create-quantum-processor-60000-times-faster-than-current-supercomputers/)

However, you may be disappointed to hear that quantum computers, at this moment, cannot even add or multiply numbers of more than 3 or 4 bits. And even if they could, their rate of operation would by no means reach 4 GHz, but more likely several MHz (a few million operations per second), at best. In other words, they're more than a thousand times _slower. _To make things worse, the information in quantum computers is extremely fragile and requires to be constantly checked and corrected, using so-called  **error correction** _. _This is a form of overhead that could make quantum computers another several orders of magnitude slower. Even in the far future, when quantum computers are more mature and more reliable, we still expect them to be much slower than the classical chips at that time.

How does this rhyme with the news about ever faster quantum computers? And why are we still interested in these slow machines? As we claimed before, we hope to do certain computations in a  **fundamentally different way**. We borrow the following analogy from Andy Matuschak and Michael Nielsen's [Quantum.country](https://quantum.country/).

<!-- ![](RackMultipart20240520-1-nfb940_html_ba0cd9c1fbfb6077.jpg) Image source: https://commons.wikimedia.org/wiki/File:STS059-238-074\_Strait\_of\_Gibraltar.jpg -->

Imagine that you'd like to travel from Morocco to Spain. If your technology does not allow you to cross the Strait of Gibraltar (say, you only have a car or a bike), your only choice is to traverse all the way through North-Africa, past the Arabian Peninsula, and through Europe, before you can reach your destination. This represents the steps taken by a classical algorithm. In the same analogy, a quantum computer endows you with the ability to traverse the sea at the Strait of Gibraltar (like a hovercraft). The fundamentally new possibilities that quantum offers allow us to do computations in _fewer steps_: even with a slower vehicle (computer), one may arrive at the destination sooner. In fact, this advantage often grows as problems become larger and more complicated. It is still an active area of research to completely map the landscape over which quantum computers can travel, and hence to determine which problems can be sped up, and which cannot.

We like this analogy in particular, because it indicates that  **some problems can profit greatly from a quantum computer, whereas many won't**: you would not want to travel by hovercraft from Amsterdam to Berlin. For this reason, we don't expect that classical computers will be 'replaced' any time soon: instead, different types of processors (classical, quantum) should synergize and work together to solve a problem as efficiently as possible.

In the analogy with the Strait of Gibraltar, the precise 'route' that you travel is the  **algorithm. ** More precisely, an algorithm is a  **step-by-step list of instructions**  that guarantee a human or a computer to find the solutions. The '_steps' _here should be sufficiently simple so that it is completely unambiguously how to do them: for example, adding, multiplying or comparing numbers. A  **quantum algorithm**  has a wider spectrum of allowed 'steps', as made possible by a quantum computer. In the end, simply finding the 'recipe' itself is not enough: the algorithm has to be turned into  **quantum software**, a piece of computer code that tells a computer explicitly how to execute the step-by-step instructions, given the possibilities and limitations of the computer hardware.

The difference between 'algorithms' and 'software' is subtle: you may think of the algorithm as a recipe to bake the perfect chocolate cookie. The algorithm should unambiguously describe the required steps to bake the cookie: what ingredients are needed, in what order they should be mixed, how long the cookie should be baked, etcetera. However, if you'd like to build a factory that produces these cookies, you need to be even more specific: out of what pipe does the dough flow, and in what pot does it have to be mixed? What exactly is the tool that performs the mixing? How are cookies laid next to each other in the oven?

Hence, the 'algorithm' is a very general solution to a problem: once found, it can be re-used different times, by different software developers. The 'software' is specific to a (type of) computer (here: the 'factory').

In the next part, we'll dive into precisely what  **quantum algorithms ** are known, and how much impact these will have.

## The applications: What problems will we solve with quantum computers?

**At a glance:**

- Key applications are expected in four areas: simulation of chemistry and materials, cracking cryptography, using quantum networks to distribute cryptographic keys, and solving large-scale optimisation and AI problems.
- Not every quantum speedup is useful: a much faster classical computer is often a better choice. In optimisation and AI, we have not found a truly valuable 'killer application' yet.

In the previous part, we saw that quantum computers are extremely slow computers, but they happen to solve some problems more efficiently, that is, in fewer steps. The most important question in this field is:  **what advantage do quantum computers have on which problems**? To answer this question, we break it down into two parts:

- [What are projected applications and use cases?](https://www.quantum.amsterdam/part-2-the-applications/#applications)
- [How large is the advantage of known speedups?](https://www.quantum.amsterdam/part-2-the-applications/#classify)

### What are projected applications and use cases?

We foresee four major use cases where quantum computing can make a real impact on society. We briefly discuss each of them here and link to a later chapter that discusses each application in more depth.

1. Simulation of other quantum systems: molecules, materials, and chemical processes

Most materials can be accurately simulated on classical computers. However, in some specific situations, the locations of atoms and electrons become notoriously hard to describe, sometimes requiring quantum mechanics to make useful predictions. Such problems are the prototypical examples of where a quantum computer can offer a great advantage. Realistic applications could be in designing new chemical processes (leading to cheaper and energy-efficient factories), estimating the effects of new medicine, or working towards materials with desirable properties (like superconductors or semiconductors). Of course, scientists will also be excited to simulate the physics that occur in exotic circumstances, like at the Large Hadron Collider or in black holes.

Simulation is, however, not a silver bullet, and quantum computers will not be spitting out recipes for new pharmaceuticals by themselves. Breakthroughs in chemistry and material science will still require a mix of theory, lab testing, computation, and most of all, the hard work of smart scientists and engineers. From this perspective, quantum computers should become a useful new tool for R&D departments.

[**Read more: How can quantum computers help us produce agricultural fertiliser more efficiently?**](https://www.quantum.amsterdam/part-3-the-search-for-a-killer-application-with-a-closer-look-at-artificial-fertilizer/)

See also:

- [Startup PhaseCraft studies the famous Fermi-Hubbard model using a quantum computer](https://www.phasecraft.io/news/phasecraft-has-achieved-a-milestone-for-quantum-computing)
- [Startup Zapata reduces the runtime and error rate of famous chemistry algorithm](https://www.zapatacomputing.com/news/robust-amplitude-estimation-experiment/)
- [IBM and Daimler research next-gen batteries](https://www.ibm.com/blogs/research/2020/01/next-gen-lithium-sulfur-batteries/)
- [Roche started a project to find medicines for Alzheimer's](https://thequantuminsider.com/2021/01/31/cqc-roche-partner-to-use-quantum-algorithms-to-tackle-drug-discovery-for-alzheimers-disease/)
- [An overview of various simulation software packages for quantum computers](https://www.linkedin.com/pulse/8-quantum-computing-packages-chemistry-simulations-2022-hariharan/)

### Here's a jump.

Here is a rough overview of quantum speedups as we understand them today, categorised by their type of speedup:

<!-- ![](RackMultipart20240520-1-nfb940_html_b19e7756b279c0.png) -->

🟢   The " **exponential**" box is the most interesting one, featuring applications where quantum computers seem to have a groundbreaking advantage over classical computers. It contains  **Shor's algorithm**  for factoring, explaining the incredible advantage that quantum computers have in codebreaking. We also believe it contains some applications in  **chemistry and material science**, especially those relating to dynamics (studying how molecules and materials change over time).

🟡   The  **"polynomial"** box is still interesting, but its applicability is unclear. Recall that a quantum computer would need much more time _per step _– and on top of that, it will have considerable overhead due to [error correction](https://www.quantum.amsterdam/part-9-why-we-need-error-correction/). Does a polynomial reduction in the number of steps overcome this slowness? According to a [recent paper](https://arxiv.org/abs/2011.04149), small polynomial speedups (as achieved by  **Grover's algorithm**) will not cut it, at least not in the foreseeable future.

🔴   For some computations, a quantum computer offers  **no speedup.** Examples include sorting a list or loading large amounts of data.

If this were the complete story, then most people would agree that quantum computing is a bit disappointing. It would be a niche product for hackers and a tiny community of physicists and chemists who study quantum mechanics itself.

⚪   Luckily, there is yet another category: many of the most exciting claims come from the  **heuristic** algorithms. This term is used when an algorithm might give a suboptimal solution (which could still be useful), or when we cannot rigorously quantify the runtime. Such algorithms are quite common on classical computers: neural networks fall in this category, and these caused a significant revolution in AI. Unfortunately, it is unclear what the impact of currently known heuristic quantum algorithms will be.

See also:

- [A quantitative analysis of Grover's runtime compared to today's supercomputers.](https://cacm.acm.org/research/disentangling-hype-from-practicality-on-realistically-achieving-quantum-advantage/)
- [(Technical!) Amazon researchers lay out a comprehensive list of end-to-end complexities of nearly every known quantum algorithm.](https://arxiv.org/abs/2310.03011)

### Where is the killer application?

For a quantum algorithm to be truly impactful, we require two properties:

1. [Useful] The algorithm solves a problem with real-world significance (for example, because organisations can work more efficiently or because it helps answer scientific questions).
2. [Better/faster] Out of all the possible approaches, this algorithm is the most attractive solution. This is achieved when a realistic quantum computer solves the problem faster than any classical machine could, but other aspects like energy consumption or total cost of hardware and software development can also play a role. This most likely requires an _exponential _speedup, or a large polynomial speedup.

Several algorithms, most notably Grover's algorithm and VQE's, have a very wide range of industrial applicability. However, it seems that in practice, other (classical) approaches solve such problems faster and more cheaply.

Then there exist exponential speedups, like the algorithm for topological data analysis, for which no practical uses have been found (despite many scientific and industrial efforts).

To our best knowledge, only codebreaking (Shor's algorithm) is both _exponentially faster_ and _extremely impactful_. Unfortunately, this is primarily a _negative _application that helps criminals – we are not aware of any positive uses of Shor, hence this is not quite the killer application that we're looking for.

Even in chemistry, it is hard to pinpoint a convincing application. Classical computers are already incredibly fast, and very good classical algorithmic techniques have been developed. Scientist Garnet Chan gives [talks](https://www.youtube.com/watch?v=DZPH7ENcRLU) which are suggestively titled "Is There Evidence of Exponential Quantum Advantage in Quantum Chemistry?".

Could the nature of quantum mechanics be such that it helps us in codebreaking, but in literally nothing else? We think that such a scenario is unlikely. It seems that a killer algorithm has not yet been found, but there are good reasons to hope that we will find one in the future. Perhaps we need novel mathematical tools, or perhaps we simply need to play around on increasingly mature quantum hardware. We hope that we'll have to incrementally update this page over the coming years, as we slowly uncover the complete set of capabilities that quantum computers have!

**Where should we look for a killer application?**

Well, we simply don't know! However, some useful technical hints may be:

- As described above, we'd most likely require an _exponential _or some _heuristic _speedup. This is much more likely achieved on problems where we don't already know very efficient classical algorithms.
- When reading data is a limiting factor (as in "big data" applications), quantum computers appear to be very slow. Getting the data into a quantum computer seems to take at least as long as processing the data on a much cheaper supercomputer. This holds, for example, when searching through a database, but also for data-intensive simulations like weather forecasting.
- Similarly, if the desired output is a large amount of data (such as a very large list or table), then a quantum computer is likely not efficient. Most quantum algorithms look at a global property of a function or dataset that can be encoded in a very small output (like Deutsch-Jozsa or Shor's algorithm when interpreted as finding the period of a function).
- Some people would say that if quantum computers are not "faster", perhaps they might solve a problem "more accurately" (for example, they might produce a more reliable forecast). However, when we look at speedups, then accuracy is already taken into account: we compare the number of steps _asserting the output has a given accuracy. _
- Classical computers are already incredibly fast, and the bottleneck for many real-world computational problems is not in a computer's speed. If an application does require a supercomputer today, then it's unlikely that anyone will invest in a quantum computer soon.
