---
layout: default
title: "The timelines: when can we expect useful quantum computers?"
nav_order: 5
---

# Timelines: When can we expect a useful Quantum Computer?

<fieldset class="field-set" markdown="1"> 
<legend class="leg-title">At a glance</legend>

The earliest quantum applications will need several million qubits,
according to the most rigorous studies.

Assuming an exponential growth similar to Moore’s Law, we predict that
these applications could be within reach around 2035-2040.

</fieldset>
**

The billion-dollar question in our field is:

*When will quantum computers outperform conventional computers on
relevant problems?*

Unfortunately, nobody really knows, and past predictions often proved
inaccurate. Moreover, a relevant quantum computer won’t just appear from
one day to another: there’s a continuous evolution where these devices
will become increasingly capable. In this chapter, we will show how we
can make a rough prediction about future timelines, and what will happen
on the path towards large-scale quantum computation.

As a small disclaimer, this chapter is very subjective: it’s not hard to
arrive at different conclusions simply by choosing different sources and
making different assumptions. I did my utmost best to rely on the most
up-to-date information, combining the fiews of the most widely accepted
papers and making assumptions that are in line with the view of most
experts.

Since I published the first estimates in 2022, I’ve seen this approach
becoming increasingly popular, with the same images presented at
conferences and Google selecting snippets from this text on certain
search queries. Hence, I have good faith that the views presented here
are among the best that we can do!

We will often refer to the goal of having a quantum computer that
outperforms a classical computer on a useful task (by being faster, more
accurate, or incurring lower costs). In this chapter, we’ll use the word
‘**utility’** to refer to this concept.

## 

## What parameters are relevant?

Compared to currently available technology, we’d require a fundamental
improvement to these specifications:

- **Number of qubits**

- **Accuracy of elementary operations (gates)**. This means that quantum
  computers have the ability to perform long computations without making
  mistakes.

There are quite a few other parameters that matter (such as the
**connectivity**, the **available set of gates**, the **speed of
operations**, and so forth). In this chapter, we choose to simplify
matters by assuming that all of these other parameters are not a
bottleneck, allowing us to focus only on the number of qubits and gate
accuracies.

### Balancing qubits and accuracies

In the previous chapter, we learned that error correction allows us to
sacrifice some fraction of qubits in exchange for better accuracies. In
fact, we expect that this will be a necessity when performing billions
of computational steps! Current estimates suggest that, for early
applications, we’ll use around a hundred to a few thousand physical
qubits for each logical qubit.

For error correction to work, we need to make some assumptions. Several
studies assume that the bare physical qubits in a quantum computer will
have gate fidelities of roughly 99.99%, which intuitively means that an
error occurs roughly every 10.000 steps. As of 2024, the largest quantum
computers hit roughly 99.90% fidelity. We still need to reduce errors by
roughly a factor of 10, but I think it’s reasonable to assume that this
can be accomplished.

If we’re willing to assume 99.99% gate fidelities *and* functioning
error correction, then we can simplify our analysis even further.
Depending on the computational problem to be solved, we can estimate the
maximum *logical* error rates that we can tolerate, and bump up the
number of qubits until that error rate has been reached. In other words,
the only remaining parameter will be the number of qubits, making the
resource estimates a lot easier.

This leads to an interesting situation. For more complex problems, we’ll
need more qubits both to store a larger amount of data and to reduce the
probability of errors so that the computation can run longer.

Isn’t the focus on just qubits a bit short-sighted? Doesn’t this create
a perverse incentive for manufacturers to focus only on qubit numbers,
forgetting about all the other parameters? Well, I would indeed be
worried that some companies can make headlines with unusable computers
that happen to have a record qubit number. But luckily, most
manufacturers seem dedicated to making the most ‘useful’ computer, and
customers will surely judge their products by the capabilities of their
logical qubits. We’re obviously making a coarse simplification here, but
making predictions about the future is hard enough as it is.

Back to the main question: When can we expect a large quantum computer?
Now that we’re only counting qubits, we can break our billion-dollar
question into two parts:

- How many qubits do we need for relevant applications?

- How long will it take before we have that many qubits?

<details markdown="1">

<summary>Wait! What exactly is this 'accuracy'?</summary>

The relevance of **accuracy **is often overlooked, perhaps because this
hardly plays a role for classical computers (which operate perfectly for
basically all intents and purposes). The problem is as follows: every
gate we perform on the quantum computer has a small chance of
introducing an error. **The more steps a computation takes, the larger
the chance that the computation fails**. In other words: harder problems
put more stringent requirements on the quantum computer’s hardware, and
require more accurate operations.

Of course, our main focus is on massive-scale computational problems
that take hours or even weeks on classical machines. 

To illustrate, imagine a quantum computer where each elementary step
(“gate”) has a 1:1000 chance to introduce an error. This computer may
suffice for computations of merely 100 gates, but as soon as of the
order of 1000 or more gates are needed, the probability that the
computer’s output is incorrect becomes quite significant.

What if we need to run a circuit of 1 million gates? If the computer has
sufficiently many qubits, we will use error correction to lower the
probability of error to much less than one-in-a-million.

We often state the ‘error’ of a gate, rather than the ‘accuracy’. For
example, a gate with 1% chance of error can be said to have 99%
‘accuracy’. Scientists like to define these numbers more precise by
talking about [gate
fidelities](https://www.quantum.amsterdam/part-5-when-can-we-expect-a-useful-quantum-computer-a-closer-look-at-timelines/quantumcomputing.stackexchange.com/questions/13198/what-does-quantum-gate-fidelity-mean) or [coherence
times](https://en.wikipedia.org/wiki/Quantum_decoherence).

Luckily, there is a well-established field of **quantum error
correction. **It allows us to combine many **‘physical
qubits’** available on the device (think of the order of 1000) into a
single, more accurate **‘logical qubit’**, on which gates have a smaller
chance of error (say, by a factor 1 billion). This allows much longer
computations. **Error correction allows a trade-off between the number
of available qubits and gate accuracy.**

For more details, [see the chapter on error
correction](https://www.quantum.amsterdam/part-9-why-we-need-error-correction/). 

</details>

##  How many qubits are needed?

In a previous chapter, we discussed the three main applications of
quantum computers: quantum simulation, breaking cryptography, and
optimisation.

The most concrete numbers can be given for **Shor’s
algorithm **(breaking cryptography), where we have a very clear problem
to tackle: obtain a private (secret) key from a widely-used
cryptosystem, like the RSA-2048 protocol. This is the perfect benchmark
because there can be no discussion about whether the problem is solved:
one either obtains the correct key, or one doesn’t. Moreover, we’re
quite convinced that even the best classical computers can’t solve the
problem (or else you shouldn’t use internet banking or trust software
updates). 

A [recent
estimate](https://quantum-journal.org/papers/q-2021-04-15-433/) finds
that a plausible quantum computer would require roughly **20
million** ‘reasonably good’ physical qubits to factor a 2048-bit number.
The whole computation would take about 8 hours[^8]. Such estimates
require several assumptions on what a quantum computer would look like
in the future. In this case, the authors assume qubits are built using
superconducting circuits, which are laid out in a square grid. Error
correction is assumed to be done using the so-called surface code,
assuming the best-known methods for error correction in 2020. Note that
future breakthroughs could reduce the required time and number of qubits
even further.

For **chemistry and material simulation**, it’s a lot harder to give
estimates, because there is not just a single problem to tackle here:
one typically uses computers to gradually improve our understanding of a
complex structure or chemical reaction. This should be combined with
theoretical reasoning and practical experiments. Moreover, classical
computers are often able to perform the same computations that the
quantum computer would make, at the cost of making certain assumptions
or simplifications. There’s a fuzzy region between ‘classically
tractable’ and ‘quantum advantage’.

The most concrete task is to compute the energy of certain molecular
configurations. The benchmark is to provide energies more accurately
than done in conventional experiments: one canonically takes the
‘chemical accuracy’ of roughly 1 kcal/mol as the precision to beat.
Then, of course, we should focus on molecules where classical computers
cannot already achieve such accuracies.   

Note that the accuracy of a chemical energy should not be confused with
the accuracy of a quantum gate, which is a whole different number.

A highly promising and well-studied benchmark problem is the simulation
of the so-called FeMo cofactor, in short: FeMoco. This molecule is
relevant when bacteria produce Ammonia (NH3), a compound that is of
great relevance to a plant’s root system. A better understanding of this
process could help us reduce the [ridiculously large carbon
emissions](https://climate.mit.edu/explainers/fertilizer-and-climate-change) now
associated with the production of artificial fertilizer. We give more
details in a separate chapter. 

Simulating FeMoco is believed [to require around **4 million
qubits**](https://journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.2.030305) (and
around 4 days of computation for a single simulation run). The
assumptions of the hardware and error correction are similar to those of
Shor’s algorithm: the estimate is based on a square grid of
superconducting qubits, using surface code to correct errors.

For a different enzyme, namely cytochrome P450, it [has been estimated
that around **5 million** qubits are
needed](https://www.pnas.org/doi/10.1073/pnas.2203533119) (again taking
roughly 4 days of computation). Altogether, we conclude that a couple
million qubits (of sufficiently high quality) can make quantum computers
relevant for R&D in chemistry. 

Some tasks that are mainly of interest for scientific purposes, such as
simulating models of quantum magnets, can be achieved with fewer
resources. Under similar assumptions, simulating a 2D transverse field
Ising model is estimated to take [just under 1 million
qubits](https://arxiv.org/abs/2211.07629).

For many **optimization problems**, it’s practically impossible to give
reasonable estimates. For one, a true killer algorithm for optimization
problems is not known yet. The algorithms that are presented as the most
promising are often *heuristic, *meaning that scientists do not know how
long an algorithm will take to find solutions. This can happen, for
example, when an algorithm repeats a certain loop until a stopping
criterion has been met.

This may come as a shock, considering the many news items that report
how quantum computers may
already [solve](https://www.volkswagenag.com/en/news/stories/2019/11/where-is-the-electron-and-how-many-of-them.html) practical [problems](https://thequantumdaily.com/2021/11/01/jp-morgan-chase-bank-research-team-bring-portfolio-optimization-a-step-closer-in-nisq-era/).
But don’t be fooled: these articles state that quantum
computers *can* indeed solve relatively simple problems, but often fail
to mention that there exist *different *approaches by which classical
computers can solve the same problems much, much faster. 

Many optimization problems have a plethora of potential solutions, but
the goal is to find the *optimal* solution (say, the one that incurs the
least costs or gets you to your destination the fastest). The solution
space is often so large that we don’t even know if we hit the optimal
solution, but we’re okay with finding one that’s *pretty close. *Several
papers claim that a quantum computer already finds solutions *faster*,
but in all cases, worrying sacrifices were made for the optimality of
the solutions.

One of the leading sources of wild claims is D-Wave’s quantum annealer.
This is a ‘limited’ quantum computer that cannot run every quantum
algorithm, but it’s extremely good at one specific algorithm called
“quantum annealing”. With around 5000 qubits, it can handle reasonably
large problems, and several companies have tried their hands at this
machine. The results obtained through today’s quantum annealing
approaches are likely also achieved by putting a similar amount of
effort into a good classical method.

We can summarize our conclusions in the table below.

| **Application** | **How well can we estimate qubit requirements?** | **Use case example** | **Qubits needed?** | **Gate error assumed?** |
|----|----|----|----|----|
| Breaking cryptography | Good | Cracking RSA-2048 | ~ 20 million | ~ 0.1% |
| Chemistry | Reasonable | Simulation of FeMoco | ~ 4 million | ~ 0.1% |
|  |  | Simulation of P450 | ~ 5 million | ~ 0.1 % |
| Optimization / AI | Bad | ? | ? |  |


[^8]: How to factor 2048 bit RSA integers in 8 hours using 20 million
    noisy qubits; Craig Gidney, and Martin Ekerå, Quantum 5, 433 (2021),
    https://quantum-journal.org/papers/q-2021-04-15-433/

### What about future improvements?

It seems almost inevitable that methodologies to break cryptography and
simulate molecules will improve. On the other hand, it’s impossible to
estimate by how much. Will we reduce qubit requirements by a few per
cent? Or by a factor of ten? By a factor of one thousand?

Some sources actually try to extrapolate the reduction in required
qubits over time (like Youtube science educator Veritasium[^9] and a
report by McKinsey[^10]), but this is such a wonky linky line over
incrompehensive scales that we will follow this strategy.

We observe that, in error correction techniques alone, there appears to
be steady progress to improve methodologies (see the chapter on
challenges in hardware). These can lower the number of physical qubits
needed, and set a lower bar for other parameters (like gate accuracies
or connectivity). Based on discussions with scientists, lowering the
qubit requirements by a factor of 3 to 10 seems plausible. Hence, for
optimistic readers, we can set another target at around 400.000 qubits
(which seems at a similar scale as early simulations for theoretical
physics models).

| **Application** | **How well can we estimate qubit requirements?** | **Use case example** | **Qubits needed?** | **Gate error assumed?** |
|----|----|----|----|----|
| Chemistry (Optimistic) | Reasonable | Simulation of FeMoco (with 10x improved methods) | ~ 400.000 | ~ 0.1 % |
| Science | Reasonable | 2D Transverse field Ising model | ~ 900.000 | ~ 0.1 % |


[^9]: See <https://www.youtube.com/watch?v=-UrdExQW0cs&t=1024s>,
    starting at 17:04.

[^10]: McKinsey Quantum Technology Monitor 2024,
    <https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/steady-progress-in-approaching-the-quantum-advantage>

## 

## 

## Can noisy algorithms be good enough?

Current quantum computers are somewhat small and not yet capable of
large-scale error correction: they are Noisy Intermediate-Scale Quantum
(NISQ) devices. An important question is: can we already achieve any
utility with such noisy devices before we achieve large-scale error
correction? That is one of the most disputed topics in our field, and
therefore it deserves some attention.

There seems to be a large effort from startups and enterprises to cook
up applications with a convincing advantage, even on noisy devices. This
noble effort would massively increase the overall usefulness of quantum
computers. So far, their findings have convinced some experts, but most
remain extremely sceptical about NISQ utility.

Maryland-based professor Sankar Das Darma underlines this picture in his
opinion article “Quantum computing has a hype problem”.[^11] He states
about NISQ that “the commercialization potential is far from clear”,
pointing at the unsatisfying evidence behind several claims in finance,
machine learning and drug discovery.

Several consultants made ridiculous claims about how tiny machines would
see an exponential advantage over enormous supercomputers. Now that the
field is coming of age, many are becoming more careful. To illustrate,
when looking back at a 2021 report, BCG chivalrously admits[^12]:

> “Our assumptions for near-term value creation in the NISQ era,
> however, have proved optimistic and must be revised.”

The most serious claim about NISQ utility comes from a Nature
publication by the IBM team, in a paper called “Evidence for the utility
of quantum computing before fault tolerance”.[^13] However, their
arguments were quickly refuted by further studies that simulated IBM’s
impressive quantum experiment on a conventional laptop.[^14]

Most experts seem to keep an eye on NISQ applications but will agree
that no utility for NISQ machines has been found yet. An overview
article about [pharmaceutical
applications](https://www.nature.com/articles/s41567-024-02411-5)[^15]
has a careful yet suggestive message:

> “Most NISQ algorithms \[…\] rely heavily on classical optimization
> heuristics, and the actual run time is difficult to estimate.
> Furthermore, recent results suggest that in NISQ approaches, the
> number of measurements required to achieve a given error scales
> exponentially with the depth of the circuit. For these reasons, here
> we focus our discussion exclusively on fault-tolerant quantum
> computers.”

Similarly, a
[recent](https://pubs.acs.org/doi/10.1021/acs.chemrev.8b00803)
overview[^16] of quantum chemistry seems to remain agnostic with regards
to NISQ advantage while pointing out that fault-tolerance has a higher
chance of succeeding.

> “… it is difficult to predict when or if algorithms on near-term noisy
> intermediate-scale quantum devices will outperform classical computers
> for useful tasks. But it is likely that, at some point, the
> achievement of large-scale quantum error correction will enable the
> deployment of a host of so-called error-corrected quantum algorithms”

In this book, we follow the view of most authorities in the field by
playing it safe and sticking to the well-understood use cases for early
fault-tolerant quantum computers that we discussed previously. We can
not rule out new breakthroughs that allow NISQ utility, but we’re
unwilling to gamble that they will happen. Any such breakthrough could
completely stir up our fragile prediction – but so would unexpected
backlashes in hardware development or even unforeseen funding stops.

[^11]: <https://www.technologyreview.com/2022/03/28/1048355/quantum-computing-has-a-hype-problem/>

[^12]: <https://www.bcg.com/publications/2024/long-term-forecast-for-quantum-computing-still-looks-bright>

[^13]: <https://www.nature.com/articles/s41586-023-06096-3>

[^14]: <https://arxiv.org/abs/2306.16372>

[^15]: Santagati, R., Aspuru-Guzik, A., Babbush, R. et al. Drug design
    on quantum computers. Nat. Phys. 20, 549–557 (2024).
    <https://doi.org/10.1038/s41567-024-02411-5>

[^16]: Quantum Chemistry in the Age of Quantum Computing, *Chem.
    Rev.* 2019, 119, 19, 10856–10915,
    <https://pubs.acs.org/doi/abs/10.1021/acs.chemrev.8b00803>

## 

## How long until we have million-qubit machines?

Now that we’ve set our target to roughly a million qubits, we’d like to
estimate when such hardware will be available. We highlight the
following sources:

1.  Road maps and claims of hardware manufacturers

2.  Surveys to experts

3.  Extrapolation of Moore’s law

### What do manufacturers say?

Below, we see the qubit numbers that several manufacturers have already
realized (solid disks) and what they will produce in the future
according to their public road maps (opaque plusses). Note that the
vertical axis is logarithmic, so it displays a very broad range from ~10
to ~10.000 qubits. A lower number of qubits does by no means indicate
that these computers are worse. In fact, the machines with the lower
numbers of qubits on this graph happen to have an important edge in
other parameters, such as gate accuracies and qubit connectivity.

<img src=" {{ site.baseurl }}/media/image14.png"
style="width:4.22469in" />

Next to their road maps, companies sometimes make more daring claims in
media interviews or at presentations at large events. Based on the
application targets above, it should be no surprise that manufacturers
shoot for around a million qubits as a ‘moonshot’ accomplishment. Back
in 2020, IBM claimed to reach the 1 million qubit target by 2030[^17].
Around the same time, Google was interpreted by journalists to do this
even faster (around 2029[^18]). The start-up PsiQuantum, which made
waves thanks to record-high investments of over a billion dollars for
their photonic quantum chips, went as far as claiming to have a million
qubits by 2025[^19].

It seems that these claims were a bit too ambitious. In 2024, with only
a year to go and no publicly presented product progression whatsoever,
PsiQuantum shifted its 1 million qubit road map to 2027[^20]. IBM took
an even more conservative step, where it’s now claiming to have just
100.000 qubits in 2033[^21] (although this machine should meet the error
correction features that we dreamingly assumed in the previous
sections). Although this delay sounds disappointing, hardware
manufacturers are still making impressive progress, as the number of
qubits grows faster than one would predict according to Moore’s Law for
classical chips!

Companies working on trapped ion machines tend to have fewer qubits, but
higher gate accuracies. Perhaps this is why
[IonQ](https://ionq.com/posts/december-09-2020-scaling-quantum-computer-roadmap) displays
its road map in a different format: they aim to have 1024 so-called
[algorithmic qubits](https://en.wikipedia.org/wiki/Quantum_volume) by
2028[^22]. This means that IonQ will have *at least *this number of
qubits, but also guarantees sufficient gate accuracy to be able to run
reasonably long circuits. It’s unclear whether a simple form of error
correction may be needed to achieve this. If so, the actual number of
physical qubits may be some orders of magnitude
higher. [Quantinuum](https://www.honeywell.com/us/en/news/2020/10/get-to-know-honeywell-s-latest-quantum-computer-system-model-h1) (previously
working under the name Honeywell) makes less concrete predictions but
expects fault-tolerant computing by 2030[^23] (meaning that significant
error correction is in place).

[^17]: <https://fortune.com/2020/09/15/ibm-quantum-computer-1-million-qubits-by-2030/>

[^18]: <https://quantumcomputingreport.com/google-goal-error-corrected-computer-with-1-million-physical-qubits-by-the-end-of-the-decade/>

[^19]: <https://www.nextbigfuture.com/2020/04/psiquantum-targets-million-silicon-photonic-qubits-by-2025.html>;
    https://www.icvtank.com/newsinfo/629365.html

[^20]: <https://quantumcomputingreport.com/psiquantum-receives-940-million-aud-620m-usd-to-install-a-1-million-qubit-machine-in-australia-by-2027/>

[^21]: <https://www.iotworldtoday.com/industry/ibm-details-road-to-100-000-qubits-by-2033>

[^22]: https://ionq.com/posts/december-09-2020-scaling-quantum-computer-roadmap

[^23]: https://www.honeywell.com/us/en/news/2020/10/get-to-know-honeywell-s-latest-quantum-computer-system-model-h1

### What does Moore’s law say?

One could assume that quantum computers will ‘grow’ at a similar rate as
classical computers. Moore’s law states that the number of transistors
in a dense integrated circuit grows exponentially: the number doubles
roughly every two years. This has been a surprisingly accurate predictor
for the development of classical IT. If we apply Moore’s law to quantum,
to get from one thousand to one million would take around 20 years –
predicting that the million-qubit mark won’t be passed until 2044.
Clearly, most hardware manufacturers are more optimistic. If we assume
the number of qubits doubles each year, one would predict that
1-million-qubit machines will be available in ten years. While doubling
a quantum computer’s size each year is already a daunting challenge,
companies like IBM and Pasqal and QuEra set the bar even higher for
themselves, hoping to double every 7-9 months.

### What do experts say?

The Global Risk Institute conducts yearly surveys asking experts to
state the *likelihood* that quantum computers pose a significant threat
to public-key cryptography 5 years from now. Similarly, respondents
would also estimate the likeliness 10, 15, 20, and 30 years away.

This essentially boils down to the question*: when will a quantum
computer run Shor’s algorithm to crack RSA-2048?* We previously saw that
around 20 million qubits would be needed for this (although experts may
take into account that this number can still be reduced).

We consider this an important source because many important authorities
in the field (like professors and corporate leaders) take part in this
study. The results from December 2023[^24], gathered from 37
participants, are displayed below.

<img src=" {{ site.baseurl }}/media/image15.png" style="width:5.27992in"
alt="threat timeline expert estimates" />

<details markdown="1">

<summary>**How to read this graph?**</summary>

Let’s look at the column labeled ‘5 years’. A total of 24 correspondents
indicate that there is less than 1% chance that quantum computers pose a
security threat in the next five years. A single person is quite
pessimistic and assigns \>70% chance that this will happen. On average,
experts say that there’s a fairly small chance that quantum computers
will pose a threat to cryptography in the next 5 years. 

Further to the right, the ratios shift: looking at 20 years from now,
the majority of experts believe that quantum computers pose a serious
threat: over half of them assign a likelihood of 70% or more.

</details>

It appears that the majority of experts believe that the tipping point
is between 10-20 years from now. Somewhere between 15 and 20 years away,
there’s a point where the median participant assigned roughly 50% chance
to see a quantum computer capable of breaking cryptographic
codes. However, we should take into account a significant uncertainty:
several experts make wildly varying estimates, so there’s no obvious
conclusion from this data.

These experts are likely aware of hardware manufacturer’s road maps, as
we shall see below.

[^24]: https://globalriskinstitute.org/publication/2023-quantum-threat-timeline-report/

## Putting it all together

In the infographic below, we present all of our findings in a single
graph.

<img src=" {{ site.baseurl }}/media/image16.png"
style="width:6.26806in" />

Assuming that qubit numbers will grow exponentially (and that all other
parameters will keep up accordingly), we can consider several scenarios.
A pessimistic scenario would be that the number of qubits ‘merely’
follows the classical version of Moore’s Law, and qubit numbers double
only once every two years (dotted line). Then, we’d have to wait well
past 2040 to even reach 100.000 qubits.

An extremely optimistic outlook would follow the blue dashed line (which
extrapolates the progress by IBM, doubling their qubits every ~9
months). If one also believes in useful applications with much less than
a million qubits, then we may be able to run these around 2030.

An intermediate perspective is to assume that the number of qubits
doubles annually. Interestingly, this seems to be roughly in line with
IBM’s latest claims and the typical expert opinion. Depending on the
application, it would mean that quantum chemistry simulation and
codebreaking canbe within reach between ~2033 and 2040.

To conclude, our estimates strongly depend on the assumptions that
you’re willing to accept (who would’ve thought!). Do you believe that
improvements in algorithms and error corrections will allow for
applications with much less than a million qubits? How quickly do you
believe that the hardware will improve? If you force me to make a
prediction, I’d say the first applications arise between 2035 and 2040,
with the understanding that there’s a huge margin for error.

As a final remark, a full utility-scale quantum computer requires much
more than a growth in the number of qubits. To reach the first useful
applications, we likely require simultaneous progress in algorithmics,
software, gate accuracies, error correction techniques, fridges, lasers,
and many other important subfields of quantum computing. Hopefully, all
these disciplines will find the required breakthroughs that will enable
the exponential growth of quantum computing hardware.

## Further reading:

- Scientist Samuel Jaques (Waterloo) makes insightful graphs that
  combine the number of qubits *and* the error rates, and puts them in
  the perspective of what is required for various applications.
  <https://sam-jaques.appspot.com/quantum_landscape_2023>



