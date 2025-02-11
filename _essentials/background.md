---
layout: default
title: "2. The background: why are we so enthusiastic about quantum?"
nav_order: 3
---
 
 
# The background: Why are we so enthusiastic about quantum technology? 
{: .no_toc }


Reading time: 13 minutes
{: .fs-3 .floatr }

### Contents
{: .no_toc }
{: .mini-header } 

- TOC
{:toc}




<fieldset class="field-set" markdown="1"> 
<legend class="leg-title mini-header">At a glance</legend>

Quantum technology is an umbrella term for devices that exploit quantum phenomena such as superposition and entanglement. The most notable innovations are expected in computers, networks, sensors, and simulators.

Quantum computers can have a speed advantage thanks to their ability to run quantum algorithms, which solve specific problems in much fewer steps than conventional methods. However, quantum computers are expected to have relatively low clock speeds, so the algorithmic advantage must be significant before a practical speedup manifests itself.

</fieldset> 
 <hr> 

## What is quantum technology?

Quantum physics, the rules that dictate the behaviour of the tiniest particles, has already proven itself as an invaluable basis for new technologies. Without this scientific theory, many invaluable tools like LED lighting, MRI scanners and solar cells may not have been invented. And it’s still relevant to push the limits of innovation, with [nano-size vehicles](https://www.rug.nl/news/2019/12/molecular-motors-and-switches?lang=en) that consist of just a few atoms [or ever-smaller transistors](https://www.nature.com/articles/nature.2012.9747) on computer chips on the horizon.

Just ahead of us is a new paradigm, which we’ll call **quantum technology**. The distinguishing factor is that it goes beyond merely building stuff from small particles. Quantum technology is about devices that perform certain processes in a fundamentally different way. That is, the data (or operations) we work with can have special properties unique to quantum physics, such as superposition and entanglement.

In our jargon, we will refer to ‘classical’ technology for devices that don’t carefully exploit the possibilities of quantum physics – they are based on ‘classical’ physics that we’re used to from high school. Your laptop and phone are examples of classical computers, and they’re connected to the classical internet. The internal transistors and electrical circuits might be so tiny that quantum physics is relevant there, but the fundamental point is that the information that they process is purely classical. Whereas classical computers work with ‘bits’, quantum technology will need a different type of information carrier that itself can be controlled at a quantum-mechanical level. We’ll call these objects ‘quantum bits’, or ‘qubits’ for short.

Within the field of quantum technology, we distinguish four categories:

- **Quantum computers** are devices that use quantum physics to perform automatic calculations to solve a problem. Computing is considered the most impactful application for most organisations, hence it’s the main focus of this book. 

- **Quantum networks** are connections between quantum devices over which *qubits* (or similar forms of quantum data)* *can be transmitted. The most relevant use case is to strengthen the cryptography used by classical computers, but there are many more applications.

- **Quantum sensors** are devices that exploit the effects of quantum physics to accurately measure certain quantities, such as a magnetic field or the strength of the Earth’s gravity. Quantum clocks also fall into this category. 

- **Quantum simulators** are devices similar to quantum computers, except that they specialise in solving a limited set of problems. Typically, they are built to reproduce the behaviour of atoms and electrons in a specific molecule or a piece of material, allowing us to measure properties like energies and reaction rates.

Each of these categories accomplishes a different goal or functionality. For now, we’ll remain agnostic about how they are built – it will be a task for hardware engineers to figure out how our desired functionality is best implemented. Since all these devices have to deal with quantum-mechanical processes under the hood, it is not uncommon that they use similar building blocks. In this book, we mainly focus on **computers **and **networks** because these seem to have the biggest impact on typical (business) users.

## The importance of high-performance computing

The abundance of cheap computational power has given humanity incredible wealth. We automated the most tedious tasks to free up time for leisure and to solve other urgent problems. It allowed us to scale factories, supply chains, and logistics to unprecedented sizes, allowing us to transport resources around the globe at minimal costs. Thanks to computer-aided design, the performance of computer chips, aeroplane wings, heart monitors, and LCD screens has improved with every generation.

Today, our computers are already incredibly fast. In fact, for many applications, there is little economic gain in making these computers even faster. Decades-old machines can successfully oversee factory operations, and writing a text document or scheduling a meeting with eight busy colleagues is not limited by the speed of your computer in any way.

However, this book is specifically about the applications where we are still hungry for more computational power. For example, by feeding more data into weather models, forecasts can become more accurate. If staff rostering would take less time, we could take more last-minute changes into account. Accurate predictions of drug reactivity in the human body could save on costly medical trials and reduce the time to market. Machine learning models like ChatGPT are still demanding more training hours to produce more sophisticated results.

It should be clear that we’re not talking about computations that happen on your laptop. We’re thinking of problems where somehow there’s value in investing in the fastest possible computers on Earth. This is the domain of **high-performance computing (HPC)**, colloquially called *supercomputers***.** Merely looking at the market, there seems to be incredible value in computing stuff: companies and academics spend tens of billions of dollars on them,[^2] and hardware suppliers like Nvidia have rapidly grown to become among the most valuable companies. We should keep a close eye on this field because the kinds of problems that are now being crunched in HPC are likely to be the ones where radically new computational tools like quantum computers can have the biggest commercial impact.

[^2]: See e.g. <https://www.marketsandmarkets.com/Market-Reports/Quantum-High-Performance-Computing-Market-631.html> and <https://www.mordorintelligence.com/industry-reports/cloud-high-performance-computing-hpc-market>.

## Why can quantum computers have an advantage? 

A naive view of quantum computers is that they’re simply *faster* than their conventional cousins. Or perhaps one may naively point at Moore’s law: with transistors reaching atomic scales, we run into quantum effects, so quantum physics may help us make better chips. However, none of these are our core motivations for looking at quantum computers. 

When we talk about a computer’s speed, most people will refer to its clock speed: the number of basic computational steps that a single processor core can complete in one second. Unfortunately, it seems unlikely that quantum computers will catch up with classical machines in terms of raw clock speed any time soon, partly because the speed of a modern CPU is already spectacular. A modern desktop processor, or even the one in your phone, works at a rate of several GHz, that is, several billions of steps per second. In each of these steps, a broad palette of operations can be applied to astronomically large numbers – modern chips work with 64-bit values, meaning that numbers up to 18,446,744,073,709,551,615 can be processed. Each of these elementary steps can be something like addition, multiplication, a comparison, etc., and we have powerful tools to weave these basic operations together to form efficient software.

Now, quantum computers are supposed to be even faster, right? Well, it’s not hard to find support for that claim: 

<img src="/img/background/headline1.png  " alt="A quantum computing headline.  " style="width:6in  ">

<img src="/img/background/headline2.png  " alt="A quantum computing headline.  " style="width:6in  ">

{: .caption }  
News headers by Techradar[^3] and IFLScience[^4].

You may be disappointed to hear that, as of 2024, quantum computers cannot even add or multiply numbers of more than 3 or 4 bits. And even if they could, their rate of operation would by no means reach several GHz, but more likely several MHz (a few *million* operations per second) at best. In other words, they’re more than a thousand times *slower. *To make things worse, the information in quantum computers is extremely fragile and needs to be constantly checked and corrected using so-called **error correction***. *This is a form of overhead that could make quantum computers another several orders of magnitude slower. Even in the far future, when quantum computers are more mature and more reliable, we still expect them to be much slower than the classical chips at that time. 

How does this rhyme with the news about ever-faster quantum computers? And why are we still interested in these slow machines? As we claimed before, we hope to do certain computations in a **fundamentally different way**. Let’s look at a beautiful analogy that Andy Matuschak and Michael Nielsen bring up in their online course [Quantum Country](https://quantum.country/)[^5]. 

<img src="/img/background/mediterranean_v3_web.png  " alt="Quantum algorithms can intuitively have an advantage because they solve a problem in fewer steps, crossing less distance.  " style="width:6..4in  ">

Imagine that you’d like to travel from Morocco to Spain, which are separated by a small piece of sea called the Strait of Gibraltar. If your technology does not allow you to cross the sea, then you’d need to take a large detour, all the way through North Africa, past the Arabian Peninsula, and through Europe, before you can reach your destination. This represents the steps taken by a classical computer. In the same analogy, a quantum computer grants you the ability to traverse both land and sea (much like a hovercraft) so that you can take a much more direct route.

The beauty of quantum computation is that we have a fundamentally different way to travel (do computations), which can sometimes bring us to our destination using a shorter route (doing fewer computational steps). Even with a much slower vehicle (computer), one may arrive at the destination sooner. In fact, the quantum advantage often grows as problems become larger and more complicated.

The analogy also shows that quantum computers do not always have an advantage: you would not want to travel from Amsterdam to Berlin by hovercraft. Unfortunately, in many cases, we don’t yet know what the fastest means of transportation is. It is still an active area of research to completely map out the landscape over which quantum and classical computers can travel and to determine which problems allow a speedup, and which don’t.

For this reason, we don’t expect that classical computers will be replaced any time soon. Instead, classical and quantum processors will live side by side, and programmers will pick whichever tool is better suited to solve a certain problem. The situation could be similar to how we use graphical processing units (GPUs) today, which offer tremendous speedups for the training of artificial intelligence models but are not made to replace regular classical processors (CPUs). Perhaps we should even give quantum computers a similar abbreviation, like ‘QPU’ for Quantum Processing Unit.

In the analogy with the Strait of Gibraltar, the precise route that you travel denotes the chosen **algorithm**. In the field of computer science, an algorithm is a step-by-step list of instructions that describes how a computational problem should be solved. The ‘steps’* *here should be sufficiently simple so that it is completely unambiguous how to do them. They could be operations such as adding, multiplying, or comparing two numbers. Needless to say, the fewer steps the algorithm requires, the better.

By exploiting quantum mechanics, a quantum computer introduces new basic steps that are impossible to perform on a classical computer. For example, the previous chapter introduced quantum logic gates that generalise operations like AND and OR. Using these building blocks, we can formulate quantum algorithms that take much fewer steps than the best classical algorithm ever could!

In the end, the time needed to solve a problem can be very roughly calculated as:

$$\text{
}{\text{Time to solve a problem} = \text{time per step}\  \times \text{number of steps required}}$$

The ‘time per step’ is a property of the hardware that you use. Clearly, a faster CPU will lead to faster solutions. The ‘number of steps required’ is dictated by the algorithm. The latter is precisely how quantum computers can offer spectacular speedups. As long as the improvement in the ‘number of steps required’ compensates for the disadvantage in ‘time per step’, a quantum computer can help us solve problems in less time!

A recurring theme in this book is the search for industrially relevant quantum algorithms. This turns out to be more challenging than it seems at first sight. Quantum algorithms are built on deep and complex mathematics, rely on counter-intuitive quantum phenomena, and require inventive new methods to tackle a problem. Simple tweaks to existing classical algorithms are rarely sufficient. In fact, for most problems, no quantum speedups have been identified at all, despite the best attempts by scientists worldwide. We might go as far as to say that, even if we had a large-scale quantum computer today, its value would be limited. For this reason, the ongoing development of novel algorithms is exceedingly important.

[^3]: Wyciślik-Wilson, S.E. (2019) ‘*Google creates quantum chip millions of times faster than the fastest sup*ercomputer’, *TechRadar*. <https://www.techradar.com/news/google-creates-quantum-chip-millions-of-times-faster-than-the-fastest-supercomputer>.

[^4]: Dunhill, J. (2021) ‘Chinese Scientists Create Quantum Processor 60,000 Times Faster Than Current Supercomputers’, *IFLScience*. <https://www.iflscience.com/chinese-scientists-create-quantum-processor-60000-times-faster-than-current-supercomputers-61475>.

[^5]: Matuschak, A. and Nielsen, M. (2019) ‘*Quantum Country’*. <https://quantum.country>.

## From algorithm to software

In the end, simply finding a good algorithm is not enough: it has to be turned into software, a piece of language that explicitly tells a computer how to execute the step-by-step instructions.

The difference between ‘algorithms’ and ‘software’ is subtle. An algorithm is a purely mathematical description that describes precisely how numbers should be manipulated. It could tell which two numbers must be multiplied, what function must be evaluated, or how an image must be transformed. However, different computers can use different types of processors and memory, and an algorithm does not describe how these operations are done *on a specific computer.* This is where software comes into play. It describes precisely what hardware operation must be called, where each number is stored in memory, and how an image is represented in binary.

As an analogy, you may think of the algorithm as a recipe to bake the perfect chocolate cookie. The algorithm should unambiguously describe what should happen to the ingredients: in what order they should be mixed, how long they should be heated at what temperature, etc. However, to build a factory that produces these cookies, you need to be even more specific: Where is the sugar stored? Out of what pipe does the dough flow? How are cookies laid next to each other in the oven?

Fundamentally, core scientific breakthroughs come from finding new algorithms. Once a new algorithm is found, it can be re-used many different times on any capable machine (assuming a good software developer will turn it into appropriate code!).

In this book, we care less about quantum software and more about quantum algorithms. Firstly, the algorithms tell us precisely the functionality that quantum computers can offer. Moreover, we don’t yet know how a mature quantum computer will be programmed or how quantum hardware and software will change in the following years. On the other hand, once a new algorithm is found, it can be cherished forever.

Now that we have come to appreciate algorithms, it is natural to ask *which* quantum algorithms we know of. What problems do quantum computers solve well? And how do these algorithms compare to their classical equivalents? This will be the topic of the next chapter.

## Further reading

- (Youtube) [*The Map of Quantum Computing*](https://www.youtube.com/watch?v=-UlxHPIEVqA) is a 30-minute overview video by Domain of Science that forms a great supplement to this book. 

- Chris Ferrie’s book [*What You Shouldn't Know About Quantum Computers*](https://arxiv.org/abs/2405.15838) debunks several myths about quantum computers, presented in an accessible way.

- Are you looking for a much more extensive and technical source that covers pretty much everything there is to know about quantum computers? French consultant Olivier Ezratty has written a 1500+ page book, [*Understanding Quantum Technologies*](https://www.oezratty.net/wordpress/2024/understanding-quantum-technologies-2024/).

