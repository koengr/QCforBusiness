---
layout: default
title: 1 Applications in chemistry and material science
nav_order: 1
---

## Applications in chemistry and material science

Perhaps the most credible application of quantum computers is to study
of quantum physics itself, and how it drives the behaviour of
microscopic systems like molecules, materials, or even sub-atomic
particles. As far back as 1981, physicist Richard Feynman ended a
conference talk with a famous
[quote](https://link.springer.com/article/10.1007/BF02650179), hinting
at the opportunities of quantum computing[^29]:

> *“I'm not happy with all the analyses that go with just the classical
> theory, because nature isn't classical, dammit, and if you want to
> make a simulation of nature, you'd better make it quantum
> mechanical”.*

Since then, scientists found increasingly sophisticated algorithms to
mimic nature on quantum devices. In this chapter, we will address the
impact quantum computing may have on chemistry and material science,
discuss the most relevant algorithms, and analyze why the enzyme FeMoco
receives such widespread attention.

[^29]: Feynman, R.P. Simulating physics with computers. *Int J Theor
    Phys* **21**, 467–488 (1982). https://doi.org/10.1007/BF02650179

### What problems in chemistry and material science will we solve? 

The computational problems that chemists care about typically come in
two flavours. The most studied problem is finding the arrangement of
particles that has the lowest possible energy, which we call the *ground
state*. In nature, we often find a system in (or close to) its ground
state. In the context of molecules, the atomic nuclei are relatively
heavy, while the lightweight electrons move much faster and are more
prone to be entangled or in a quantum superposition. Therefore, chemists
tend to make approximations that allow them to focus primarily on the
positions and spins of the electrons: the *electronic structure
problem.*

The other problem is about dynamics: given some initial configuration of
particles, how do they reconfigure themselves after a certain amount of
time? This is often referred to as the *(time) evolution* of a system.
Both problems are often informally referred to as *‘quantum
simulation’*.

We often receive the question: why is it so hard to simulate quantum
mechanics on a *classical* computer? Intuitively, the problem arises
when we deal with many particles that exhibit large amounts of
superposition and entanglement, such that the location of one particle
is heavily dependent on the (undecided) position of many other
particles. We call such states *strongly correlated*. The computational
problems arise because we may need to keep track of all the possible
locations that particle A can be, but also all the locations of particle
B, and the same for particle C, etcetera, which quickly winds up to an
*exponential* number of possible sets of conditional locations. In other
words, the number of relevant *amplitudes* (see the section <u>What is
quantum?)</u> that we need to keep track of, grows very quickly. Even
with a mere one hundred particles, brute-force simulation is far beyond
the capabilities of the world’s best supercomputers.

It is a common misconception that quantum computers straightforwardly
offer an exponential advantage compared to classical computers for all
chemistry problems. An influential recent
[paper](https://www.nature.com/articles/s41467-023-37587-6)
reports[^30]:

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
work around the classical computer’s bottlenecks, which has raised a
high bar before a quantum computer can meaningfully compete. For nearly
every problem in chemistry, there appears to be a clever trick to run
this somewhat efficiently on a classical machine. For a quantum killer
application, we likely need to search in a fairly specific niche, right
at the sweet spot where classical methods struggle while a quantum
computer excels. It is not entirely clear how large this niche is, and
it is an active research area to identify more systems where classical
methods fall short. To illustrate, a recent [review
article](https://www.nature.com/articles/s41567-024-02411-5)
states[^31]:

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
model](https://www.nature.com/articles/s41586-022-04940-6)[^32].

Looking at more commercially relevant applications, the aforementioned
multi-metal systems are often cited, which are relevant to calculating
ligand binding affinities in drugs and understanding the mechanism
behind the biological production of ammonia. We study the latter example
at the end of this chapter. Another potential area could be to
understand and search for high-temperature, superconductors[^33]. It is
hard to say what the impact of quantum computers will be beyond these
niche areas, as this will depend strongly on the usefulness of small
polynomial speedups and unpredictable breakthroughs in quantum
algorithms. We see a broad palette of applications that are proposed,
such as water splitting (to efficiently produce hydrogen as fuel),
carbon capture mechanisms[^34], the study of efficient solar cells and
the development of higher capacity batteries.

[^30]: Lee, S., Lee, J., Zhai, H. et al. Evaluating the evidence for
    exponential quantum advantage in ground-state quantum chemistry. Nat
    Commun 14, 1952 (2023). https://doi.org/10.1038/s41467-023-37587-6

[^31]: Santagati, R., Aspuru-Guzik, A., Babbush, R. et al. Drug design
    on quantum computers. Nat. Phys. 20, 549–557 (2024).
    <https://doi.org/10.1038/s41567-024-02411-5>

[^32]: Daley, A.J., Bloch, I., Kokail, C. et al. Practical quantum
    advantage in quantum simulation. Nature 607, 667–676 (2022).
    <https://doi.org/10.1038/s41586-022-04940-6>

[^33]: Garnet Kin-Lic Chan, Quantum chemistry, classical heuristics, and
    quantum advantage (preprint); <https://arxiv.org/abs/2407.11235>

[^34]: Von Burg et al., Quantum computing enhanced computational
    catalysis, Phys. Rev. Research 3, 033055.
    <https://journals.aps.org/prresearch/abstract/10.1103/PhysRevResearch.3.033055>

### Algorithms for quantum chemistry

Three quantum methods deserve to be mentioned. The first is the
[**Trotter-Suzuki**](https://en.wikipedia.org/wiki/Time-evolving_block_decimation)
method, sometimes called ‘Trotterization’, which simulates time
evolution. In this case, we assume that the initial state is encoded in
the qubits of the quantum computer. The Trotter-Suzuki method is
guaranteed to return a good approximation of the state at a later time,
again encoded in the qubit registers.

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
is the [**variational quantum eigensolver
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
(QMC)](https://en.wikipedia.org/wiki/Quantum_Monte_Carlo), although
these are too slow to address very large systems such as drugs[^35].

A typical workflow for finding a ground state on a quantum computer
could be as follows: We construct a quantum circuit that first performs
a VQE, followed by QPE on the output of the variational circuit. This
way, the output of the circuit represents the energy of the state
produced by the VQE. We then allow a classical optimiser to run this
circuit many times, gradually changing the parameters of the VQE until
the lowest possible energy is found.

Needless to say, there exist various more technical and more
sophisticated methods, for which we refer to other more technical
sources, such as:

TODO

[^35]: “Current classical quantum-chemistry algorithms fail to describe
    quantum systems accurately and efficiently enough to be of practical
    use for drug design.”, Santagati, R., Aspuru-Guzik, A., Babbush,
    R. *et al.* Drug design on quantum computers. *Nat. Phys.* **20**,
    549–557 (2024). <https://doi.org/10.1038/s41567-024-02411-5>.

### A hype around quantum computing for climate changes

Some sources make spectacular (but extremely dubious) claims about how
quantum computing could be a key ingredient to solve climate change,
thanks to the boost to R&D on batteries, carbon capture, and more
efficient chemical processes. But McKinsey takes the biscuit with their
report titled “Quantum computing just might save the planet”[^36]. We’ll
remain agnostic as to whether the impact of chemistry R&D is really
sufficient to save the planet, but the claim of quantum computing as a
saviour is especially ridiculous because it will still take several
years before these machines are sufficiently mature. To limit global
warming to no more than 1.5° C, we need to take action much sooner.
Imperial College London writes on their website[^37], referencing the
2014 IPCC report:

> “Limiting warming to 1.5°C will only be possible if global emissions
> peak within the next few years, and then start to decline rapidly,
> halving by 2030.”

At the same time, our chapter on timelines shows that it is exceedingly
unlikely that serious quantum utility in chemistry R&D is possible
anywhere before the 2030s.

Nevertheless, it’s interesting to look at one of the ‘killer
applications’ often mentioned in this context: a use case that has
both 1) a convincing quantum speedup and 2) serious real-world impact.
We’ll zoom in on the molecule FeMoco, which precisely has a multi-metal
system that classical methods struggle with. To understand the relevance
of this molecule, we need to dive into the world of food production.

[^36]: https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/quantum-computing-just-might-save-the-planet

[^37]: https://www.imperial.ac.uk/grantham/publications/climate-change-faqs/how-and-when-do-we-need-to-act-on-climate-change-/

### A case study of a promising enzyme: FeMoco

<img src=" {{ site.baseurl }}/media/image17.png"
style="width:1.33333in" />

{{ begin figure caption }}

Chemical structure of the FeMo cofactor, taken from Wikimedia.

{{ end figure caption }}

Today’s agriculture relies heavily on the use of artificial fertilizer
to grow our crops. Without large-scale use of supplementary nutrients,
it would be problematic to feed our world’s huge population. In fact,
about [half of the nitrogen
atoms](https://cen.acs.org/articles/86/i33/Haber-Bosch-Reaction-Early-Chemical.html) in
our body have previously passed a fertilizer factory!

Unfortunately, the production of fertilizer involves enormous energy
consumptions and carbon emissions. The main culprit is the ingredient
ammonia (NH3), of which we use as much as [230 Mton per
year](https://www.statista.com/statistics/1065865/ammonia-production-capacity-globally/).
Although our air consists mainly of molecular nitrogen (N2), plants
cannot directly absorb this. Instead, they rely on bacteria (or, in the
case of artificial fertilizer, humans) to perform so-called nitrogen
fixation, breaking the strong triple bond of molecular nitrogen and
converting this into ammonia. Microorganisms can convert this into
further nitrogen-containing compounds that can be absorbed by the root
system.

Pretty much all of the world’s ammonia production follows the so-called
Haber-Bosch process, where hydrogen gas (H2) and nitrogen gas (N2) react
together to form ammonia. The process can be implemented in large,
high-yield production lines, but also comes with a major disadvantage:
its staggering energy consumption. This is mainly due to two essential
steps: producing sufficiently pure hydrogen and nitrogen gasses, and
later separating the H2 and N2 molecules into individual atoms. The
latter is especially challenging for N2 due to its strong triple bond.
To achieve this, factories operate at extreme conditions, with high
temperatures (~400 degrees Celsius) and high pressure, largely driven by
natural gas. As much as [1.8% of the world’s CO2
emission](https://royalsociety.org/topics-policy/projects/low-carbon-energy-programme/green-ammonia/) is
caused by factories performing such reactions, consuming around 3-5% of
the world’s natural gas production!

Can’t this be done more efficiently? In this case, we strongly suspect
so. Certain bacteria are also capable of making ammonia, but in a much
more efficient way: without high temperatures or high pressure. It would
be extremely valuable to copy this trick.

To imitate the bacteria, we need to better understand a particular
substance, the FeMo cofactor (short: FeMoco), which acts as a catalytic
active site during ammonia production. A perfect simulation of FeMoco is
not possible on classical computers, as the structure of roughly 120
strongly reacting electrons rapidly becomes intractable. [Researchers
from ETH Zurich and
Microsoft](https://www.pnas.org/content/114/29/7555) were the first to
recognize that a quantum computer may aid in a more accurate study of
FeMoco. A few years later, researchers at Google gave a more concrete
prediction: with about [4 million qubits and 4 days of computing
time](https://www.quantum.amsterdam/part-3-the-search-for-a-killer-application-with-a-closer-look-at-artificial-fertilizer/o%09https:/journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.2.030305),
a single simulation could be accomplished.

With FeMoco, we seem to finally have an example that confidently ticks
all the boxes for quantum utility: classical methods are limited, we
have well-understood quantum methods, and computational results have a
significant commercial and societal impact. Unfortunately, there is yet
another catch -- innovation never comes so easily. [A recent
article](https://arxiv.org/abs/2407.11235)[^38] quotes that industrial
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
magically spit out recipes for fertilizers, nor for medicines,
batteries, or catalysts. For real breakthroughs, we need a team of
chemists, engineers, and other experts, who spend several years to run
experiments, have discussions, employ computer simulations, make
mistakes, go back to the drawing board a few times, and slowly converge
to practical solutions. We should not forget that quantum computers
merely provide a new set of tools. The best we can hope for is that
smart people will use them in the right way!

Further reading:

- (Scientific article) Toward the first quantum simulation with quantum
  speedup <https://www.pnas.org/doi/10.1073/pnas.1801723115>

- (2022 review article) Prospects of quantum computing for molecular
  sciences
  <https://link.springer.com/article/10.1186/s41313-021-00039-z>

- (2019 review article) Quantum Chemistry in the Age of Quantum
  Computing <https://pubs.acs.org/doi/10.1021/acs.chemrev.8b00803>

[^38]: Garnet Kin-Lic Chan, Quantum chemistry, classical heuristics, and
    quantum advantage (preprint); https://arxiv.org/abs/2407.11235

