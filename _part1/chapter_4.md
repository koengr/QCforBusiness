---
layout: default
title: 4 The applications, What problems will we solve with quantum computers?
nav_order: 4
---

## The applications: What problems will we solve with quantum computers?

<fieldset class="field-set" markdown="1"> 
<legend class="leg-title">At a glance</legend>

- Four key applications in IT are: simulation of chemistry and
  materials, cracking cryptography, using quantum networks to distribute
  cryptographic keys, and solving large-scale optimization and AI
  problems. 

- Not every quantum speedup is useful: a much faster classical computer
  is often a better choice. In optimisation and AI, we have not found a
  truly valuable ‘killer application’ yet.

</fieldset>

In the previous chapter, we saw that quantum computers are extremely
slow computers, but they happen to solve some problems more efficiently,
that is, in fewer steps. The most important question in this field
is: **what advantage do quantum computers have on which problems**?

The [Quantum Algorithm Zoo](https://quantumalgorithmzoo.org/)[^3] lists
pretty much all known quantum algorithms. It has grown into an
impressive list that cites over 400 papers. Unfortunately, upon closer
inspection, it’s hard to extract precisely the useful business
applications from it, for various reasons. Several algorithms solve
highly artificial problems for which no real business use-cases are
known. Others may make unrealistic assumptions or may only offer a
speedup in the formal number of computational steps (but not in actual
wall clock time). Nevertheless, it’s definitely recommended to scroll
through.

For this book, we take a different approach. We focus specifically on
algorithms with plausible business applications. To assess their
advantage, we break our main question down in two parts:

- What are projected applications with a quantum speedup?

- How large is the advantage of known speedups?

[^3]: https://quantumalgorithmzoo.org/

### What are projected applications with a quantum speedup?

We foresee four major use cases where quantum computing can make a real
impact on society. We briefly discuss each of them here and link to a
later chapter that discusses each application in more depth. 

#### 1. Simulation of other quantum systems: molecules, materials, and chemical processes

Most materials can be accurately simulated on classical computers.
However, in some specific situations, the locations of atoms and
electrons become notoriously hard to describe, sometimes requiring
quantum mechanics to make useful predictions. Such problems are the
prototypical examples of where a quantum computer can offer a great
advantage. Realistic applications could be in designing new chemical
processes (leading to cheaper and energy-efficient factories),
estimating the effects of new medicine, or working towards materials
with desirable properties (like superconductors or semiconductors). Of
course, scientists will also be excited to simulate the physics that
occur in exotic circumstances, like at the Large Hadron Collider or in
black holes.

Simulation is, however, not a silver bullet, and quantum computers will
not be spitting out recipes for new pharmaceuticals by themselves.
Breakthroughs in chemistry and material science will still require a mix
of theory, lab testing, computation, and most of all, the hard work of
smart scientists and engineers. From this perspective, quantum computers
have the potential to become a valued new tool for R&D departments.

[**Read more: How can quantum computers help us produce agricultural
fertiliser more
efficiently?**](https://www.quantum.amsterdam/part-3-the-search-for-a-killer-application-with-a-closer-look-at-artificial-fertilizer/)

See also:

- [Startup PhaseCraft studies the famous Fermi-Hubbard model using a
  quantum
  computer](https://www.phasecraft.io/news/phasecraft-has-achieved-a-milestone-for-quantum-computing)

- [Startup Zapata reduces the runtime and error rate of famous chemistry
  algorithm](https://www.zapatacomputing.com/news/robust-amplitude-estimation-experiment/)

- [IBM and Daimler research next-gen
  batteries](https://www.ibm.com/blogs/research/2020/01/next-gen-lithium-sulfur-batteries/)

- [Roche started a project to find medicines for
  Alzheimer’s](https://thequantuminsider.com/2021/01/31/cqc-roche-partner-to-use-quantum-algorithms-to-tackle-drug-discovery-for-alzheimers-disease/)

- [An overview of various simulation software packages for quantum
  computers](https://www.linkedin.com/pulse/8-quantum-computing-packages-chemistry-simulations-2022-hariharan/)

#### 2. Cracking a certain type of cryptography

The security of today’s internet communication relies heavily on a
cryptographic protocol invented by Rivest, Shamit and Adleman
([RSA](https://en.wikipedia.org/wiki/RSA_(cryptosystem))) in the late
70s. The protocol helps distribute secret encryption keys (so that
nobody else can read messages in transit) and guarantees the origin of
files and webpages (so that you know that the latest Windows update
actually came from Microsoft, and not from some cybercriminal). RSA
works thanks to an ingenious mathematical trick: honest users can set up
their encryption using relatively few computational steps, whereas
‘spying’ on others would require one to solve an extremely hard problem.
For the RSA cryptosystem, that problem is *prime factorisation, *where
the goal is to decompose a very large number (for illustration purposes,
let’s think of 15) into its prime factors (here: 3 and 5). As far as we
know, for sufficiently large numbers, this task can take a classical
computer such a long time that nobody would ever succeed in breaking a
relevant code – think of thousands of years. RSA was deemed adequately
secure, at least, until computer scientist Peter Shor discovered that
quantum computers are quite good at factoring.  
  
The quantum algorithm by Shor can crack RSA (and also its cousin
called [elliptic curve
cryptography](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography))
in a relatively efficient way using a quantum computer. To be more
concrete, according to [a
recent](https://arxiv.org/abs/1905.09749) paper, a plausible quantum
computer could factor the required 2048-bit number in roughly 8 hours
(and using approximately 20 million imperfect qubits). The authors had
to make several assumptions about what a future quantum computer would
look like, and did so in a very prudent way: picking realistic
properties of prospective hardware, and using the most up-to-date
knowledge of error correction and compiling. Note that future
breakthroughs will likely further reduce the stated time and qubit
requirements.

Luckily, not all cryptography is broken as easily by a quantum computer.
RSA falls in the category of[ *public key
cryptography*](https://en.wikipedia.org/wiki/Public-key_cryptography)*, *which
delivers a certain range of functionalities. A different class of
protocols is *[symmetric key
cryptography](https://en.wikipedia.org/wiki/Cryptography#Modern_cryptography),* which
is reasonably safe against quantum computers but doesn’t provide the
same rich functionality as *public key *crypto. The most sensible
approach is replacing RSA with so-called [post-quantum
cryptography](https://en.wikipedia.org/wiki/Post-quantum_cryptography) (PQC):
public-key cryptosystems resilient to attackers with a large-scale
quantum computer. Interestingly, PQC does *not* require honest users
(that’s you) to have a quantum computer: it will work perfectly fine on
today’s PCs, laptops and servers.

[**Read more: How will quantum computers impact
cybersecurity? **](https://www.quantum.amsterdam/part-8-the-impact-on-cybersecurity/)

See also:

- [MinutePhysics has a fantastic (but technical!) explainer of Shor’s
  algorithm](https://www.youtube.com/watch?v=lvTqbM5Dq4Q). 

- [NIST’s competition to standardize new public-key
  algorithms](https://csrc.nist.gov/projects/post-quantum-cryptography/post-quantum-cryptography-standardization)   

- Nature feature article: [The race to save the Internet from quantum
  hackers](https://www.nature.com/articles/d41586-022-00339-5)

 

During the following decade, every large organisation will have to worry
about updating to post-quantum cryptography – a complex migration that
comes in addition to the many existing cybersecurity threats. The
American National Institute of Standards and Technology (NIST) runs a
competition to select a new standard that is adequate for most
applications. Nevertheless, many organisations run a vast amount of
legacy software that is hard to update, so completing this update in the
upcoming [~8
years](https://www.quantum.amsterdam/part-5-when-can-we-expect-a-useful-quantum-computer-a-closer-look-at-timelines/) poses
a complex operational challenge. For this reason, organisations are
encouraged to start this process as early as possible. 

A new type of cryptography poses additional risks: it has not yet been
tested as thoroughly as the nearly 50-year-old RSA standard. Ideally,
new implementations will be *hybrid*, meaning that they combine the
security of a conventional and a post-quantum algorithm. On top of that,
organisations are encouraged to adopt *cryptographic agility*, meaning
that cryptosystems can be easily changed or updated if the need arises. 

[**Read more: What steps should your organisation
take?**](https://quantum.amsterdam/part-6-getting-started)

Other great sources are:

- [The PQC Migration
  Handbook](https://english.aivd.nl/publications/publications/2023/04/04/the-pqc-migration-handbook),
  written by the Dutch secret service AIVD and research organizations
  CWI and TNO.

- Cloudflare [tracks the adoption of post-quantum
  cryptography](https://blog.cloudflare.com/pq-2024) and explains many
  technical details extremely well. 

- US National Institute for Standards and Technology (NIST): [Getting
  Ready for Post-Quantum Cryptography: Explore Challenges Associated
  with Adoption and Use of Post-Quantum Cryptographic
  Algorithms](https://csrc.nist.gov/publications/detail/white-paper/2021/04/28/getting-ready-for-post-quantum-cryptography/final)

- UK National Cyber Security Center: [Preparing for Quantum-Safe
  Cryptography](https://www.ncsc.gov.uk/whitepaper/preparing-for-quantum-safe-cryptography)

- BSI (German secret service): [Quantum-safe cryptography –
  fundamentals, current developments and
  recommendations](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Publications/Brochure/quantum-safe-cryptography.html?nn=916626)

- NCSC (Dutch National Cyber Security Center): [Factsheet
  Postquantumcryptografie
  \[NL\]](https://www.ncsc.nl/binaries/ncsc/documenten/factsheets/2019/juni/01/factsheet-postkwantumcryptografie/20170831+Factsheet-Postkwantumcryptografie-v1.1.pdf)

#### 3. Quantum Key Distribution to strengthen cryptography

Out of all the applications for quantum networks, Quantum Key
Distribution (QKD) is the one to watch. It allows two parties to
generate secure cryptographic keys together, which can then be used for
everyday needs like encryption and authentication. It requires a quantum
network connection that transports photons in fragile quantum states.
Such connections can currently reach a few hundred kilometres, and there
is a clear roadmap to expand to a much wider internet. The most likely
usage will be as an “add-on” for high-security purposes (such as
military communication or data exchange between data centres), in
addition to standard post-quantum cryptography. 

Unfortunately, we often see media articles suggesting that QKD is a
solution to the threat of Shor’s algorithm and that it would form an
‘unbreakable internet’. Both claims are highly inaccurate. Firstly, QKD
does not offer the wide range of functionality that public-key
cryptography offers, so it is not a complete replacement for the
cryptosystems broken by Shor. Secondly, there will almost certainly be
ways to hack a QKD system (just like with any other security system).
Then why bother with QKD? The advantage of QKD is based on one main
selling point: contrary to most other forms of cryptography, it does not
rely on mathematical assumptions. This can be an essential factor when
someone is highly paranoid about their cryptography, or when data has to
remain confidential for an extremely long period of time. 

At this time, pretty much every national security agency discourages the
use of QKD simply because the available products are far from mature
(and because PQC should be prioritised). It is unclear how successful
QKD could be in the future—we will discuss this in depth in a next
chapter.  
  
[**Read more: What are the use cases of quantum
networks?**](https://www.quantum.amsterdam/part-4-the-applications-of-quantum-networks/)

See also: 

- [A short video explainer about how QKD
  works.](https://www.youtube.com/watch?v=2kdRuqvIaww&ab_channel=QuantumVisions%28WWUM%C3%BCnster%29)

- [The NCSC states that it “does not endorse the use of QKD for any
  government or military
  applications”](https://www.quantum.amsterdam/%E2%80%A2%09https:/www.ncsc.gov.uk/whitepaper/quantum-security-technologies)

- [The French ANSSI, German BSI, Dutch NLNCSA and Swedish SNCSA
  published a critical position paper on QKD in
  2024. ](https://www.bsi.bund.de/SharedDocs/Downloads/EN/BSI/Crypto/Quantum_Positionspapier.html)

----

Quote:

Major security agencies do not support the use of QKD to secure
communications and agree that post-quantum cryptography should be
regarded as the best way to mitigate the quantum threat.

**THE PQC MIGRATION HANDBOOK**

<img src=" {{ site.baseurl }}/media/image11.png" style="width:1.81786in"
alt="Screenshot 2023 05 09 at 17.54.18" />

End quote

----

We firmly warn that other security products with the word “quantum” in
the name are no guarantee for protection against Shor’s algorithm. In
particular, “[quantum random number
generators](https://en.wikipedia.org/wiki/Hardware_random_number_generator)”
(QRNGs) are sometimes promoted as a saviour against the quantum threat,
which is nonsense. These devices serve a completely different purpose:
they compete with existing hardware to generate unpredictable secret
keys, which find a use (for example) in [hardware security
modules](https://en.wikipedia.org/wiki/Hardware_security_module) in data
centres. 

See also: 

- [Samsung builds QRNGs into certain phones on the South Korean
  market. ](https://www.sammobile.com/news/galaxy-a-quantum-launched-south-korea-sk-telecom-exclusive/)

#### 4. Optimisation and machine-learning

This is the part where most enterprises get excited: Can we combine the
success of AI and machine learning with the radically new capabilities
of quantum computers? Classical optimisation and AI techniques have had
an incredible impact in many areas, from optimising train schedules to
detecting fraud, from training chatbots to accurately predicting the
weather. 

Under the hood, all such applications are based on concrete mathematical
problems such as (discrete) optimisation, differential equations,
classification, and optimal planning. For conciseness, we collectively
refer to these problems (including machine learning tasks)
as *‘optimisation’*. The classical field of optimisation is of great
importance and takes up a significant fraction of the world’s
computational resources!  
  
Contrary to the many classical successes, the impact of quantum
optimisation or machine learning is not yet clear. To better understand
the available algorithms, we will consider three different categories. 

**Rigorous but slow algorithms**

Many quantum optimisation algorithms have a well-proven *quantum
speedup: *there is no dispute that these require *fewer* *computational
steps* than any classical algorithm. For instance, a famous quantum
algorithm invented by [Lov
Grover](https://en.wikipedia.org/wiki/Grover's_algorithm) (with
extensions by [Durr and Hoyer](https://arxiv.org/abs/quant-ph/9607014))
finds the maximum of a function in fewer steps than conventional
brute-force search. Similarly, quantum speedups were found for popular
computational methods such
as [backtracking](https://arxiv.org/abs/1509.02374), [gradient
descent](https://arxiv.org/abs/1711.00465), [semidefinite
programming](https://arxiv.org/abs/1710.02581), [lasso](https://arxiv.org/abs/2110.13086),
and [interior point methods for solving differential
equations](https://arxiv.org/abs/1512.05903). 

The main question is whether this also means that the quantum computer
requires less *time*! All of the above optimisation algorithms offer a
so-called *polynomial speedup *(in the case of Grover, this is sometimes
further specified to be a *quadratic speedup*). As we will soon see, it
is not entirely clear if these speedups are enough to compensate for the
slowness of a realistic quantum computer – at least in the foreseeable
future. 

*  
***Heuristic algorithms  
**  
On the other hand, some algorithms claim much larger speedups, but there
is no undisputed evidence to back this up. Often, these algorithms are
tested on small datasets using the limited quantum computers available
today – which are still so tiny that not much can be concluded about
larger-scale problems. Nonetheless, these ‘high risk, high reward’
approaches typically make the bold claims that receive media attention.
The most noteworthy variants are:

- [Variational quantum
  circuits](https://pennylane.ai/qml/glossary/variational_circuit/) (VQC)
  are relatively short quantum programs that a classical computer can
  incrementally change. In jargon, these are quantum circuits that rely
  on a set of free parameters. The classical computer will run these
  programs many times, trying different parameters until the quantum
  program behaves as desired (for example, it might output very good
  train schedules or accurately describe a complex molecule). The
  philosophy is that we squeeze as much as possible out of small quantum
  computers with short-lived qubits: the (fast) classical computer takes
  care of most of the computation, whereas the quantum computer runs
  just long enough to sprinkle some quantum magic into the solution.  
  Although its usefulness is disputed, this algorithm is highly
  flexible, leading to quantum variants of classifiers, neural networks,
  and support vector machines. Variants of this algorithm may be found
  under different names, such as Quantum Approximate optimisation
  Algorithm (QAOA), Variational Quantum Eigensolver (VQE), and quantum
  neural networks. 

- [Quantum
  annealing](https://en.wikipedia.org/wiki/Quantum_annealing) solves a
  particular class of optimisation problems. The problem is encoded into
  a physical system (in jargon: a Hamiltonian) so that at very low
  temperatures, the physical system somehow describes a solution to the
  problem. For example, when finding the optimal locations to place
  mobile phone masts, a qubit in the state “1” might indicate a good
  site. A quantum annealing algorithm is a smart way to ‘make’ such a
  low-temperature system (often by starting in a setting where it’s
  trivial to ‘cool’ and then slowly introducing the complex forces
  corresponding to the target system).  
  Annealing itself is a mature classical algorithm. The advantage of a
  ‘quantum’ approach is not immediately apparent, although there are
  claims that hard-to-find solutions are more easily reached thanks to
  ‘quantum fluctuations’ or ‘tunnelling’.  
  Quantum annealing was popularised by the Canadian
  company [D-Wave](https://www.dwavesys.com/), which builds dedicated
  hardware with up to 5000 qubits and offers a cloud service that
  handles relatively large optimisation problems. 

 

**Fast solutions in search of a suitable problem**

Lastly, there exist algorithms with large speedups, for which we are
still looking for use-cases with any scientific or economic relevance.
The most notable example is the quantum algorithm that solves [systems
of linear equations](https://en.wikipedia.org/wiki/HHL_algorithm)[^4]
with an exponential advantage. This problem is ubiquitous in engineering
and optimization, but unfortunately there are [so many
caveats](https://doi.org/10.1038/nphys3272) that no convincing practical
use cases have been found[^5].

Recently, much attention has gone to the algorithm for [topological data
analysis](https://www.nature.com/articles/ncomms10138) (a method to
assess certain global features of a dataset), which promises an
exponential advantage under certain assumptions. Again, scientists are
still searching for a convincing application.

Similarly, a quantum version of a classical machine learning algorithm
called Support Vector Machines was found to have an [exponential
advantage over classical
methods](https://www.nature.com/articles/s41567-021-01287-z)[^6].
Unfortunately, this only works with a very specific dataset based on the
factoring problem that Shor’s algorithm is well known for, hence we see
no practical uses.

**A fourth class: quantum-inspired algorithms**

Some impressive speedups that were recently found have been
‘dequantized’: these algorithms were found to work on classical
computers too! There’s a beautiful story behind this process, where Ewin
Tang, a Master’s student at the time, made one of the largest
algorithmic breakthroughs of the decade. A great report can be found [on
Medium](https://medium.com/qiskit/how-ewin-tangs-dequantized-algorithms-are-helping-quantum-algorithm-researchers-3821d3e29c65)[^7]. 

Unfortunately, there does not yet exist an optimisation algorithm with
obvious economic value: all of them come with serious caveats. This
perspective is perhaps a bit disappointing, especially in a context
where quantum computing is often presented as a disruptive innovation.
Our main takeaway is that quantum optimisation (especially quantum
machine learning!) is rather over-hyped. 

Of course, there are still good hopes that we will find *new *algorithms
and applications. To truly understand this field, we should examine the
prospects of finding a new ‘killer algorithm’. The next section becomes
slightly more technical and helps us quantify the amount of ‘quantum
advantage’ that different algorithms have. 

 

Further reading: 

- Volkswagen and ExxonMobil used annealing to optimise routes
  for [buses](https://www.volkswagen-newsroom.com/en/press-releases/volkswagen-optimizes-traffic-flow-with-quantum-computers-5507) and [transport
  ships](https://ibm-research.medium.com/exxonmobil-ibm-scientists-explore-state-of-art-quantum-algorithms-to-solve-routing-formulations-e7ce39f8741c).

- [Professor Scott Aaronson warns us to ‘Read the fine print’ of
  optimisation
  algorithms.](https://scottaaronson.com/papers/qml.pdf) \[Appeared
  in [Nature Physics, with
  paywall](https://www.nature.com/articles/nphys3272)\] 

- [Professor Sanker Das Sarma warns of hype within the field of quantum
  optimisation and machine
  learning.](https://www.technologyreview.com/2022/03/28/1048355/quantum-computing-has-a-hype-problem/)

[^4]: Harrow, Aram W; Hassidim, Avinatan; Lloyd, Seth (2008). "Quantum
    algorithm for linear systems of equations". Physical Review Letters.
    103 (15) 150502. <https://doi.org/10.1103/PhysRevLett.103.150502>

[^5]: Aaronson, S. Read the fine print. Nature Phys 11, 291–293 (2015).
    <https://doi.org/10.1038/nphys3272>

[^6]: Liu, Y., Arunachalam, S. & Temme, K. A rigorous and robust quantum
    speed-up in supervised machine learning. Nat. Phys. 17, 1013–1017
    (2021). <https://doi.org/10.1038/s41567-021-01287-z>

[^7]: https://medium.com/qiskit/how-ewin-tangs-dequantized-algorithms-are-helping-quantum-algorithm-researchers-3821d3e29c65

### How large is the advantage of known speedups? 

When looking at the applications of quantum computers, one should always
keep in mind: Are these actual improvements over our current
state-of-the-art? Anyone can claim that their algorithm *can* solve a
problem, but what we really care about is whether it solves it *faster*.
Classical computers are already extremely fast, so quantum algorithms
should offer a substantial speedup before they become competitive. 

**{{ begin box }}**

**What does an “algorithmic speedup” mean?**

We can assess algorithms by their so-called “asymptotic complexity”: As
a problem becomes ‘bigger’, how much longer does a computation take? The
main figure of merit is how this scales towards very large sizes. 

For every instance of a problem, we can define a ‘size’ that influences
the difficulty. For example, computing 54 x 12 is much easier than
231.423 x 971.321, even though they’re technically the same problem, and
we’d use the very same [multiplication
algorithm](https://en.wikipedia.org/wiki/Multiplication_algorithm).
Similarly, creating a work schedule for a team of 5 is simpler than
dealing with 10.000 employees. We typically use the letter ‘n’ to denote
the problem size. You can see n as the number of digits in a
multiplication (like 2 or 6 above) or the number of employees involved
in a schedule. 

For some very hard problems, the time to solution takes the form of an
exponential: T ~ e<sup>n</sup>, where T is the time taken. Exponential
scaling is typically a bad thing, as the function e<sup>n</sup> becomes
incredibly large even for moderate values of n. The problem of factoring
(on a classical computer) scales [somewhat
similar](https://en.wikipedia.org/wiki/General_number_field_sieve) to T
~ e<sup>n</sup>. 

There are also problems for which the scaling looks like a polynomial,
like T ~ n<sup>3</sup> or T ~ n<sup>2</sup>. Polynomials grow much
slower than exponentials, making it easier to solve large problems in a
reasonable amount of time. The problem of factoring on a quantum
computer takes scales roughly as T ~ n<sup>3</sup> (thanks to [Shor’s
algorithm](https://en.wikipedia.org/wiki/Shor%27s_algorithm)\*). Because
a quantum computer brought the exponential down to a polynomial, we call
this an ‘**exponential speedup**’. Such speedups are a computer
scientist’s dream because they have an incredible impact on practical
runtimes. 

Often, we deal with ‘merely’ a **polynomial speedup**, which happens
when we obtain a smaller polynomial (for example, going from T ~
n<sup>2</sup> towards T ~ n), or perhaps even a ‘smaller’ exponential
function (like T ~ e<sup>n</sup> towards T ~ e<sup>n/2</sup>. Reducing
the exponent by a factor of two (like n<sup>2 </sup>-\> n) is also
sometimes called a **quadratic speedup **(which is precisely what
Grover’s algorithm gives us).

Further reading:

- At a more coarse level, we can define different [“complexity
  classes”](https://medium.com/qiskit/what-can-a-quantum-computer-actually-do-4daed0691f6b). 

   
 \* You may find even sources stating smaller polynomials, like
n<sup>2</sup> log(n). These are theoretically possible but rely
on [asymptotic
optimizations](https://en.wikipedia.org/wiki/Sch%C3%B6nhage%E2%80%93Strassen_algorithm) that
are unlikely to be used in practice.

**{{ end box }}**

Here is a rough overview of quantum speedups as we understand them
today, categorised by their type of speedup:

 

<img src=" {{ site.baseurl }}/media/image12.png"
style="width:6.26806in" />

🟢   The “**exponential**” box is the most interesting one, featuring
applications where quantum computers seem to have a groundbreaking
advantage over classical computers. It contains **Shor’s algorithm** for
factoring, explaining the incredible advantage that quantum computers
have in codebreaking. We also believe it contains some applications
in **chemistry and material science**, especially those relating to
dynamics (studying how molecules and materials change over time). 

🟡   The **“polynomial” **box is still interesting, but its
applicability is unclear. Recall that a quantum computer would need much
more time *per step *– and on top of that, it will have considerable
overhead due to [error
correction](https://www.quantum.amsterdam/part-9-why-we-need-error-correction/).
Does a polynomial reduction in the number of steps overcome this
slowness? According to a [recent
paper](https://arxiv.org/abs/2011.04149), small polynomial speedups (as
achieved by **Grover’s algorithm**) will not cut it, at least not in the
foreseeable future. 

🔴   For some computations, a quantum computer offers **no
speedup. **Examples include sorting a list or loading large amounts of
data. 

If this were the complete story, then most people would agree that
quantum computing is a bit disappointing. It would be a niche product
for hackers and a tiny community of physicists and chemists who study
quantum mechanics itself. 

⚪   Luckily, there is yet another category: many of the most exciting
claims come from the **heuristic **algorithms. This term is used when an
algorithm might give a suboptimal solution (which could still be
useful), or when we cannot rigorously quantify the runtime. Such
algorithms are quite common on classical computers: neural networks fall
in this category, and these caused a significant revolution in AI.
Unfortunately, it is unclear what the impact of currently known
heuristic quantum algorithms will be. 

In summary, we see that the utility of the mentioned quantum
applications is unclear – but some are more unclear than others. The
following graph summarises this well: the most ‘valuable’ applications
(like quantum machine learning) also come with the largest risks,
whereas the most convincing speedups (like codebreaking) offer less
value. The applications of chemistry and material science sit somewhere
in between.

<img src=" {{ site.baseurl }}/media/image13.png"
style="width:5.16239in" />

Unfortunately, we don’t dare to assign concrete numbers to this graph.
That’s something that we will need to empirically find out in the near
future.

See also:

- [A quantitative analysis of Grover’s runtime compared to today’s
  supercomputers.](https://cacm.acm.org/research/disentangling-hype-from-practicality-on-realistically-achieving-quantum-advantage/) 

- [(Technical!) Amazon researchers lay out a comprehensive list of
  end-to-end complexities of nearly every known quantum
  algorithm.](https://arxiv.org/abs/2310.03011)

### Where is the killer application?

For a quantum algorithm to be truly impactful, we require two
properties: 

1.  \[Useful\] The algorithm solves a problem with real-world
    significance (for example, because organisations can work more
    efficiently or because it helps answer scientific questions).

2.  \[Better/faster\] Out of all the possible approaches, this algorithm
    is the most attractive solution. This is achieved when a realistic
    quantum computer solves the problem faster than any classical
    machine could, but other aspects like energy consumption or total
    cost of hardware and software development can also play a role.
    Ideally, the quantum computer enjoys an *exponential *speedup, or at
    least a large polynomial speedup. 

Several algorithms, most notably Grover’s algorithm, have a very wide
range of industrial applicability. However, it seems that in practice,
other (classical) approaches solve such problems faster and more
cheaply. 

Then there exist exponential speedups, like the algorithm for
topological data analysis, for which no practical uses have been found
(despite many scientific and industrial efforts). 

To our best knowledge, only codebreaking (Shor’s algorithm) is
both *exponentially faster* and *extremely impactful*. Unfortunately,
this is primarily a *negative *application that helps criminals – we are
not aware of any positive uses of Shor, hence this is not quite the
killer application that we’re looking for. 

Even in chemistry, it is hard to pinpoint a convincing application.
Classical computers are already incredibly fast, and very good classical
algorithmic techniques have been developed. Scientist Garnet Chan
gives [talks](https://www.youtube.com/watch?v=DZPH7ENcRLU) which are
suggestively titled “Is There Evidence of Exponential Quantum Advantage
in Quantum Chemistry?”. 

Could the nature of quantum mechanics be such that it helps us in
codebreaking, but in literally nothing else? We think that such a
scenario is unlikely. It seems that a killer algorithm has not yet been
found, but there are good reasons to hope that we will find one in the
future. Perhaps we need novel mathematical tools, or perhaps we simply
need to play around on increasingly mature quantum hardware. We hope
that we’ll have to incrementally update this page over the coming years,
as we slowly uncover the complete set of capabilities that quantum
computers have!

