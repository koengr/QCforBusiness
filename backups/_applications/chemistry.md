---
layout: default
title: "Applications in chemistry and material science"
nav_order: 1
toc: true
---

# Applications in chemistry and material science

{% include components/page-toc.html %}


Perhaps the most credible application of quantum computers is to study
quantum physics itself. This helps us deepen our understanding of
microscopic systems like molecules, atoms, or even sub-atomic particles,
ultimately leading to the discovery of new drugs, materials and chemical
production methods. At first sight, there seems to be a significant
advantage compared to conventional computers, which struggle to store
the complex quantum state of systems with many particles. As far back as
1981, physicist Richard Feynman ended a conference talk with a famous
[quote](https://link.springer.com/article/10.1007/BF02650179), hinting
at the opportunities of quantum computing[^41]:

> *“I'm not happy with all the analyses that go with just the classical
> theory, because nature isn't classical, dammit, and if you want to
> make a simulation of nature, you'd better make it quantum
> mechanical”.*

Since then, scientists have become increasingly adept at accurately
controlling quantum systems. Today, universities boast a wide spectrum
of analogue quantum experiments that help us understand nature under
exotic circumstances. We’re now lining up our tools to take these
simulations to the next level: studying nature with digital quantum
machines.

In this chapter, we will assess how quantum computers can impact the
fields of chemistry and material science. That makes this chapter more
technical, and we’ll assume some (very) basic background in chemistry
and physics. We discuss the most relevant algorithms, evaluate claims
about quantum computing’s benefits in the fight against climate change,
and analyse why the enzyme FeMoco receives such widespread attention.

[^41]: Feynman, R.P. Simulating physics with computers. *Int J Theor
    Phys* **21**, 467–488 (1982). https://doi.org/10.1007/BF02650179

## What problems in chemistry and material science will we solve? 

The computational problems that chemists care about typically come in
two flavours. The most studied problem is finding the arrangement of
particles with the lowest possible energy, which we call the *ground
state*. In nature, we often find a system in (or close to) its ground
state. In the context of molecules, the atomic nuclei are relatively
heavy, while the lightweight electrons move much faster and are more
prone to be entangled or in a quantum superposition. Therefore, chemists
tend to make approximations that allow them to focus primarily on the
positions and spins of the electrons: the *electronic structure
problem.*

The other problem is about dynamics: given some initial configuration of
particles, how do they reconfigure themselves after a certain amount of
time? This is often referred to as a system's *(time) evolution*. Both
problems are often informally referred to as ***quantum simulation***.

We often receive the question of why it’s so hard to simulate quantum
mechanics on a *classical* computer. Intuitively, this hardness arises
when we deal with many particles that exhibit large amounts of
superposition and entanglement, such that the location of one particle
is heavily dependent on the (undecided) position of many other
particles. We call such states *strongly correlated*. Classical
computers struggle because they need to keep track of all the possible
locations that particle A can be, but also all the locations of particle
B, and the same for particle C, etcetera, which quickly winds up to an
*exponential* number of possible sets of conditional locations. In other
words, the number of relevant *amplitudes* (see the [chapter on quantum
physics](https://quantumcomputingforbusiness.com/essentials/quantum/))
that we need to keep track of grows very quickly. Even with a mere one
hundred particles, brute-force simulation is far beyond the capabilities
of the world’s best supercomputers.

It is a common misconception that quantum computers straightforwardly
offer an exponential advantage compared to classical computers for all
chemistry problems. An influential recent
[paper](https://www.nature.com/articles/s41467-023-37587-6)
reports[^42]:

> *“\[…\] we conclude that evidence for such an exponential advantage
> across chemical space has yet to be found. While quantum computers may
> still prove useful for ground-state quantum chemistry through
> polynomial speedups, it may be prudent to assume exponential speedups
> are not generically available for this problem.”*

Note that this comment is specifically about finding *ground states,*
which is still arguably the most relevant problem in chemistry. There is
still ample evidence that quantum computers offer an exponential speedup
for *time evolutions.*

There is more bad news for quantum computers. Over the years,
computational chemists have found brilliant hacks and optimisations to
work around the classical computer’s bottlenecks, raising a high bar
before a quantum computer can meaningfully compete. For nearly every
problem in chemistry, there appears to be a clever trick to solve it
somewhat efficiently on a classical machine. For a killer application,
we likely need to search in a fairly specific niche, right at the sweet
spot where classical methods struggle while a quantum computer excels.
It is not entirely clear how large this niche is, and it is an active
research area to identify more systems where classical methods fall
short. To illustrate, a recent [review
article](https://www.nature.com/articles/s41567-024-02411-5)
states[^43]:

> *\[Classical methods struggle with\] multi-metal systems, where
> multiple metal ions are in similar electronic environments and
> interactions. These appear in some biological systems, including
> enzymes (for example, FeMoco and P450), but it is unclear how common
> they are or what the added value of an accurate system description
> would be.*

Still, there seems to be realistic hope that quantum computers can, at
the very least, make tangible contributions within niche areas. The
first end-users will most likely be scientists who study the
fundamentals of quantum systems, as is already done in physics
experiments today. We wouldn’t call these devices computers yet, but
rather ‘analogue simulators’. One of the first actual ‘computer’
applications could be to study models of quantum materials, such as the
famous [Hubbard
model](https://www.nature.com/articles/s41586-022-04940-6)[^44].

The first error-corrected quantum computers will hopefully find their
place in industrial R&D settings. One of the first application areas
could be the aforementioned multi-metal systems, which are relevant in
calculations of ligand binding affinities in drugs and in understanding
the mechanism behind the biological production of ammonia. We address
the latter example at the end of this chapter. Another exciting area
could be to explore the mechanism behind Type-II superconductivity and
to search for materials that become superconducting at even higher
temperatures[^45]. It is hard to say what the impact of quantum
computers will be beyond such niche areas, as this will depend strongly
on the usefulness of small polynomial speedups and unpredictable
breakthroughs in quantum algorithms. We see a broad palette of other
impactful applications that have been proposed, such as water splitting
(to efficiently produce hydrogen fuel)[^46], carbon capture
mechanisms[^47], the study of efficient solar cells[^48] and the
development of higher capacity batteries[^49].

[^42]: Lee, S., Lee, J., Zhai, H. et al. Evaluating the evidence for
    exponential quantum advantage in ground-state quantum chemistry. Nat
    Commun 14, 1952 (2023). https://doi.org/10.1038/s41467-023-37587-6

[^43]: Santagati, R., Aspuru-Guzik, A., Babbush, R. et al. Drug design
    on quantum computers. Nat. Phys. 20, 549–557 (2024).
    <https://doi.org/10.1038/s41567-024-02411-5>

[^44]: Daley, A.J., Bloch, I., Kokail, C. et al. Practical quantum
    advantage in quantum simulation. Nature 607, 667–676 (2022).
    <https://doi.org/10.1038/s41586-022-04940-6>

[^45]: Garnet Kin-Lic Chan, Quantum chemistry, classical heuristics, and
    quantum advantage (preprint); <https://arxiv.org/abs/2407.11235>

[^46]: <https://quantumapplicationlab.com/2024/01/08/photocatalysis-for-water-splitting/>

[^47]: Von Burg et al., Quantum computing enhanced computational
    catalysis, Phys. Rev. Research 3, 033055.
    <https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.3.033055>

[^48]: <https://www.pv-magazine.com/2023/08/04/quantum-physics-supercomputers-and-solar-cell-efficiency/>

[^49]: <https://spectrum.ieee.org/lithium-air-battery-quantum-computing>

## Algorithms for quantum chemistry

We describe three of the most important quantum simulation algorithms.
The first is the
[**Trotter-Suzuki**](https://en.wikipedia.org/wiki/Time-evolving_block_decimation)
method, sometimes called ‘Trotterization’, which simulates time
evolution. In this case, we assume that some correct initial state of
the world is encoded in the qubits of some quantum computer. The
Trotter-Suzuki method is guaranteed to return a good approximation of
the state at a later time, again encoded in the qubit registers.

The most common tool for finding a ground state is [**quantum phase
estimation
(QPE)**](https://en.wikipedia.org/wiki/Quantum_phase_estimation_algorithm),
which reports the energy of a certain quantum state. As a subroutine, it
requires some evolution method, like Trotter-Suzuki. Unfortunately, it
will only succeed in finding the ground state if it gets as input a
state that is a reasonable approximation to the ground state. This
shifts the problem to: how do we produce a good candidate for the ground
state?

The most popular algorithm for creating states with certain properties
(like very low energies) is the [**variational quantum eigensolver
(VQE)**](https://en.wikipedia.org/wiki/Variational_quantum_eigensolver).
This is an example of a variational quantum circuit: a series of gates
that can be gradually changed until the output matches certain
requirements. Just like other variational approaches, it is a heuristic
algorithm, lacking rigorous guarantees that it will produce the desired
output in a reasonable time.

Creating a good approximation to a ground state is, in general, NP-hard.
This means that it is extremely unlikely that a rigorous algorithm for
this task will be found. On the other hand, there is good hope that more
*heuristic* methods (just like VQE) will be found that work well on
certain subsets of problems (for example, the kind of molecules
frequently encountered in the human body). In fact, such heuristic
methods already form the workhorse of classical computational chemistry,
with tools such as [Density functional theory
(DFT)](https://en.wikipedia.org/wiki/Density_functional_theory),
[Configuration Interaction
(CI)](https://en.wikipedia.org/wiki/Configuration_interaction) and
[Quantum Monte Carlo
(QMC)](https://en.wikipedia.org/wiki/Quantum_Monte_Carlo). These work
for small systems but are often too slow to study large systems such as
proteins or drugs[^50]. A workaround is to apply these methods to just a
small part of the target system, employing faster but less accurate
methods to oversee the larger whole.

An example of a basic workflow to find find a ground state on a quantum
computer could be as follows. The first step is to train a VQE to output
states with low energy[^51]. These might not be the exact ground states,
but they will hopefully be very similar (in jargon, they have a large
overlap with the ground state). As a second step, we append a QPE
circuit, that will not only report the energy of the VQE states, but
also has a fair probability of changing these states into perfect ground
states (in jargon: it projects onto the ground state). Running the VQE +
QPE combination a few times will almost certainly give the lowest energy
states, assuming the VQE produces proper approximations of it.

[^50]: Santagati, R., Aspuru-Guzik, A., Babbush, R. *et al.* Drug design
    on quantum computers. *Nat. Phys.* **20**, 549–557 (2024).
    <https://doi.org/10.1038/s41567-024-02411-5>.  
    Quote from this article: “Current classical quantum-chemistry
    algorithms fail to describe quantum systems accurately and
    efficiently enough to be of practical use for drug design.”

[^51]: An interesting subtlety is how we measure the energy that the VQE
    is supposed to optimise. Luckily, there exist very short circuits
    that we can append to measure the output states in different
    *bases*. By running the VQE a relatively small number of times, we
    can make good estimates of the energy of its output states. This
    avoids performing the more complex QPE during the optimisation
    phase.

### Further reading on simulation algorithms

Various more technical and sophisticated methods exist, for which we
refer to other more technical sources. These require expert knowledge of
quantum chemistry.

- Introduction to Quantum Algorithms for Physics and Chemistry
  (2012)[^52], a pedagogical book chapter. Open version:
  <https://arxiv.org/abs/1203.1331>.

- Quantum Algorithms for Quantum Chemistry and Quantum Materials Science
  (2020)[^53], a scientific overview article. Open version:
  <https://arxiv.org/abs/2001.03685>.

[^52]: Yung, M.-H. et al. (2014) ‘Introduction to Quantum Algorithms for
    Physics and Chemistry’, in Quantum Information and Computation for
    Chemistry. John Wiley & Sons, Ltd, pp. 67–106. Available at:
    <https://doi.org/10.1002/9781118742631.ch03>.

[^53]: Bauer, B. et al. (2020) ‘Quantum Algorithms for Quantum Chemistry
    and Quantum Materials Science’, Chemical Reviews, 120(22), pp.
    12685–12717. Available at:
    <https://doi.org/10.1021/acs.chemrev.9b00829>.

## A hype around quantum computing for climate change

Some businesses make spectacular claims about how quantum computing
could be a cornerstone in solving climate change, thanks to the boost to
R&D on batteries, carbon capture, and more efficient chemical factories.
However, rarely do we see any evidence – most seem to assume that
quantum computers simply spit out blueprints for revolutionary
sustainable technologies.

McKinsey takes the biscuit with their report titled “[Quantum computing
just might save the
planet](https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/quantum-computing-just-might-save-the-planet)”[^54].
The article rightfully selects some of the most impactful technologies
to reduce CO<sub>2</sub> emissions, like electrification of transport,
improved solar panels, and even vaccines that reduce methane emissions
by cattle (indeed, due to cow farts). The article concludes that the
selected innovations could reduce global warming from 1.7-1.8 °C by 2050
down to just 1.5 °C. It is a mystery to me why they throw in quantum
computing because there is no mention whatsoever about why specifically
quantum algorithms would be the key enabling factor. This exemplifies
what we see more frequently in popular articles: quantum computers are
depicted simply as insanely fast computers that will magically solve the
barriers to other new technologies on our wishlist.

What are the true prospects for quantum computing in the context of
climate change? Sceptics will point out that technological innovations
alone will be sufficient to avert a climate disaster – we will remain
agnostic in this debate. A much more concrete issue is the mismatch in
timelines. Climate experts agree that, to limit global warming to no
more than 1.5° C, we need to take action relatively soon. Imperial
College London concludes on their website[^55], referencing the 2014
IPCC report:

> “Limiting warming to 1.5°C will only be possible if global emissions
> peak within the next few years, and then start to decline rapidly,
> halving by 2030.”

Our chapter on timelines shows that it is exceedingly unlikely that
significant quantum utility is possible anywhere before the 2030s.
Additionally, it will take several years before a computational
discovery is sufficiently mature for large-scale deployment. For this
reason, we don’t see quantum computers as a good investment against
climate change, but rather as a long-term development that can help us
tackle other problems that humanity will face in the future.

Do we really have no concrete applications in climate science? Well, we
do have some concrete leads. In the search for a killer application in
chemistry, perhaps the most-studied topic is the enzyme FeMoco. This is
precisely a multi-metal system that classical methods struggle with, and
as we’ll soon see, it appears in reputable plans for decarbonization. To
understand the relevance of this molecule, we need to dive into the
world of food production.

[^54]: https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/quantum-computing-just-might-save-the-planet

[^55]: https://www.imperial.ac.uk/grantham/publications/climate-change-faqs/how-and-when-do-we-need-to-act-on-climate-change-/

## A case study of potential killer application: FeMoco

<img src=" {{ site.baseurl }}/media/image19.png"
style="width:1.33333in" />

{: .caption }  
Figure: Chemical structure of the FeMo cofactor, taken from Wikimedia.

Today’s agriculture relies heavily on the use of artificial fertilisers.
Without large-scale use of supplementary nutrients, we would not be able
to sustain intensive farming practices and feeding our world’s huge
population would be problematic. In fact, about [half of the nitrogen
atoms](https://cen.acs.org/articles/86/i33/Haber-Bosch-Reaction-Early-Chemical.html) in
our body have previously passed a fertiliser factory!

Unfortunately, the production of fertiliser involves enormous energy
consumption and carbon emissions. The main culprit is the ingredient
ammonia (NH<sub>3</sub>), of which we use as much as [230 Mton per
year](https://www.statista.com/statistics/1065865/ammonia-production-capacity-globally/).
Although our air consists mainly of molecular nitrogen (N<sub>2</sub>),
plants cannot directly absorb this. Instead, they rely on bacteria (or,
in the case of artificial fertiliser, humans) to perform so-called
nitrogen fixation, breaking the strong triple bond of molecular nitrogen
and converting this into ammonia. Microorganisms can convert this into
further nitrogen-containing compounds that the root system can absorb.

Pretty much all of the world’s ammonia production facilities follow the
so-called [Haber-Bosch](https://en.wikipedia.org/wiki/Haber_process)
process, where hydrogen gas (H<sub>2</sub>) and nitrogen gas
(N<sub>2</sub>) react together to form ammonia. This method has the
benefit that it can be implemented in large, high-yield production lines
but comes with the disadvantage of its staggering energy consumption.
The inefficiency stems from two essential steps: first, producing
sufficiently pure hydrogen and nitrogen gasses, and later, separating
the H<sub>2</sub> and N<sub>2</sub> molecules into individual atoms.
Breaking N<sub>2</sub> is especially challenging due to its strong
triple bond. As an effect, factories operate at extreme conditions, with
high temperatures (~400 degrees Celsius) and high pressure, driven
mainly by natural gas. As much as [1.8% of the world’s CO2
emission](https://royalsociety.org/topics-policy/projects/low-carbon-energy-programme/green-ammonia/) is
caused by factories performing such reactions, consuming around 3-5% of
the world’s natural gas production!

Can’t this be done more efficiently? We strongly suspect so. Certain
bacteria are also capable of making ammonia, but in a seemingly more
efficient way, without high temperatures or high pressure. It would be
extremely valuable to copy this trick.

To imitate the bacteria, we need to better understand a particular
substance, the FeMo cofactor (short: FeMoco), which acts as a catalytic
active site during ammonia production. A perfect simulation of FeMoco is
not possible on classical computers, as the structure of roughly 120
strongly reacting electrons rapidly becomes intractable. In
2016, [researchers from ETH Zurich and
Microsoft](https://www.pnas.org/content/114/29/7555) were the first to
report that a moderately large quantum computer could come to the
rescue. A few years later, Google researchers refined the prospects even
further, describing how simulations could be accomplished with about [4
million qubits and 4 days of computing
time](https://www.quantum.amsterdam/part-3-the-search-for-a-killer-application-with-a-closer-look-at-artificial-fertilizer/o%09https:/journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.2.030305).

With FeMoco, we seem to finally have an example that confidently ticks
all the boxes for quantum utility: classical methods are limited, we
have well-understood quantum methods, and computational outputs have a
significant commercial and societal impact. Unfortunately, there is yet
another catch - innovation never comes so easily. [A recent
article](https://arxiv.org/abs/2407.11235)[^56] quotes that industrial
production of a ton of Ammonia costs around 26 GJ of energy, compared to
at least 24 GJ (estimated) in bacteria. This is indeed not the massive
reduction we were hoping for. The article concludes that perhaps the
true value lies in a better understanding of this process:

> *“The chemical motivation to study nitrogenase is thus less to produce
> an energy-efficient replacement of the Haber-Bosch process but rather
> because it is an interesting system in its own right, and perhaps it
> may motivate how to understand and design other catalysts that can
> activate and break the nitrogen-nitrogen triple-triple bond under
> ambient conditions.”*

As a final note, we want to stress that quantum computers do not
magically spit out recipes for fertilisers, nor for medicines,
batteries, or catalysts. For real breakthroughs, we need collaborations
between chemists, engineers, and many other experts who spend several
years running experiments, having discussions, employing computer
simulations, making mistakes, going back to the drawing board a few
times, and slowly converging to practical solutions. We should not
forget that quantum computers merely provide a new set of tools. The
best we can hope for is that smart people will use them in the right
way!

[^56]: Garnet Kin-Lic Chan, Quantum chemistry, classical heuristics, and
    quantum advantage (preprint); https://arxiv.org/abs/2407.11235

## Further reading

- (Scientific article) Toward the first quantum simulation with quantum
  speedup <https://www.pnas.org/doi/10.1073/pnas.1801723115>

- (2022 review article) Prospects of quantum computing for molecular
  sciences
  <https://link.springer.com/article/10.1186/s41313-021-00039-z>

- (2019 review article) Quantum Chemistry in the Age of Quantum
  Computing <https://pubs.acs.org/doi/10.1021/acs.chemrev.8b00803>

