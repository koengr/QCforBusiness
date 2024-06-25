---
layout: default
title: 1 Chemistry, A case study of artificial fertiliser
nav_order: 1
---

## Chemistry: A case study of artificial fertiliser

Perhaps the most credible applications of quantum computers is the
simulation of chemistry and material science. The advantage is
especially large when a large number of electrons engage in a complex
quantum mechanical state. In such situations, quantum mechanics is
notoriously hard to simulate on a classical computer: accurately
describing N particles requires a number of computational steps that
scales *exponentially *in N. The quantum computer is not troubled by
such inefficiencies, and scientists find [increasingly detailed
descriptions](https://www.pnas.org/doi/10.1073/pnas.1801723115) of how
one could obtain faster tools to study complicated materials and
molecules.

Again, there are good arguments to be skeptical about the impact of
quantum computers. Computational chemistry has seen many years of
developments and optimizations to work around the classical computer’s
bottlenecks, which has raised a high bar before a quantum computer can
contribute meaningful insights. A true near-term killer application is
likely to be limited to[ a very specific
niche](https://arxiv.org/abs/2009.12472), right in a sweet spot where
classical methods remain limited. For precisely these uses cases, one
may find the most concrete evidence that quantum computers can usefully
outperform classical computers. To highlight a well-studied and highly
relevant example, we dive into the world of artificial fertilizer.

### The case of FeMoco

<img src="/media/image12.png"
style="width:1.33333in;height:2.48667in" />

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

If we manage, like bacteria, to do this nitrogen fixation at room
temperature, this will save a significant percentage of the world’s
energy consumption and greenhouse gas emissions. Tom O’Brien, assistant
professor at Leiden University and researcher at Google, [was
quoted](https://www.universiteitleiden.nl/en/research-dossiers/the-quantum-computer/quantumchemie-en) that
he believes that the simulation of FeMoco is the *killer
application* for quantum computing. And indeed, it rightfully ticks both
boxes: there is a significant computational advantage and a meaningful
impact on the world. Unfortunately, we need to wait at least until the
2030s before we have a suitably large quantum computer.

As a final note, we want to stress that quantum computers do not
magically spit out recipes for fertilizers, nor for medicines,
batteries, or catalysts. For real breakthroughs, we need a team of
chemists, engineers, and other experts, who spend several years to run
experiments, have discussions, employ computer simulations, make
mistakes, go back to the drawing board a few times, and slowly converge
to practical solutions. We should not forget that quantum computers
merely provide a new set of tools. The best we can hope for is that
smart people will use them in the right way!

