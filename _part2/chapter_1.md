---
layout: default
title: 1 Chemistry, A case study of artificial fertilizer
nav_order: 1
---


*Many thanks to[ Seenivasan
Hariharan](https://www.cwi.nl/people/seenivasan-hariharan) for fruitful
discussion on this chapter.*

There are many fantastic claims about the capabilities of quantum
computers: they
may [develop](https://www.aquantum.es/the-qhealth-project-personalized-medicine-and-quantum-computing/) personalized [medicine](https://www.ibm.com/downloads/cas/8QDGKDZJ),
make [logistics](https://lot.dhl.com/quantum-computing-could-transform-the-logistics-industry-within-the-next-decade/) more [efficient](https://supplychaindigital.com/logistics/supply-chain-quantum-computing-conundrum),
and perhaps
even [solve](https://www.bcg.com/publications/2020/quantum-advantage-fighting-climate-change) the
climate [problem](https://www.zdnet.com/article/quantum-computers-could-be-a-weapon-against-climate-change-but-maybe-not-in-the-way-you-expect/).
Despite the very positive picture presented by most new articles, many
scientists are skeptical: for many of these problems, quantum computers
are not quite faster, and never is simply 'running a computation' the
core solution. In this bleak picture, we're still lacking a true *killer
application, *a certain computational problem with two important
properties:

1.  \[*Useful*\] Solving the problem has real-world significance (for
    example, because organizations can work more efficiently or because
    it helps answer scientific questions).

2.  \[*Faster*\] A realistic quantum computer would solve the problem in
    significantly less time than any classical machine could.

Several problems are known where the 'faster' requirement is fulfilled,
but which turn out to be useless. An example is a certain [quantum
walk](https://arxiv.org/abs/quant-ph/0209131) on two so-called glued
trees. Despite many scientific efforts, no practical uses have been
found for this 'solution in need of an application'.

The other way around, we have several quantum algorithms that solve
highly relevant problems, such as [Grover's famous search
algorithm](https://en.wikipedia.org/wiki/Grover%27s_algorithm). However,
the so-called 'quadratic speedup' that Grover offers is [believed to be
insufficient](https://journals.aps.org/prxquantum/abstract/10.1103/PRXQuantum.2.010103) to
stand a chance against a decently-sized classical computer -- even when
we look several decades into the future.

![glued trees
lovett2011](/media/image7.png){width="4.604166666666667in"
height="2.757093175853018in"}

The \'glued trees\' graph that was specifically conceived to obtain an
exponential quantum speedup. This application is still looking for a
pratical use. Image taken from Lovett (2011).

So, what other candidates are there that may turn out to be truly useful
algorithms?

Truly groundbreaking innovations are sometimes predicted for the fields
of optimization and machine learning. However, as we describe in [a
different
chapter](https://www.quantum.amsterdam/part-2-the-applications-of-quantum-computing-how-will-these-machines-change-society/),
there is very little hard evidence that these quantum algorithms can be
competitive with well-designed classical software -- we can safely say
that the true killer application has not been found yet.

*Further reading:*

-   [MIT professor Sanker Das Sarma warns for hype within the field of
    quantum optimization and machine
    learning.](https://www.technologyreview.com/2022/03/28/1048355/quantum-computing-has-a-hype-problem/)

Some of the most promising candidates fall in the category of chemistry
and material science, especially those where large numbers of electrons
engage in a complex quantum mechanical state. In such situations,
quantum mechanics is notoriously hard to simulate on a classical
computer: accurately describing N particles requires a number of
computational steps that scales *exponentially *in N. The quantum
computer is not troubled by such inefficiencies, and scientists
find [increasingly detailed
descriptions](https://www.pnas.org/doi/10.1073/pnas.1801723115) of how
one could obtain faster tools to study complicated materials and
molecules.

Again, there are good arguments to be skeptical: the field of
computational chemistry has seen many years of developments and
optimizations to work around the classical computer's bottlenecks, which
has raised a high bar before a quantum computer can contribute
meaningful insights. A true near-term killer application is likely to be
limited to[ a very specific niche](https://arxiv.org/abs/2009.12472),
right in a sweet spot where classical methods remain limited. For
precisely these uses cases, one may find the most concrete evidence that
quantum computers can usefully outperform classical computers. To
highlight a well-studied and highly relevant example, we dive into the
world of artificial fertilizer.

### The case of FeMoco

![](/media/image8.png){width="1.3333333333333333in"
height="2.486666666666667in"}

Chemical structure of the FeMo cofactor, taken from Wikimedia.

Simulation of FeMoco is slowly becoming the C. Elegans of quantum
computing: a particularly well-studied example that might become a
reference for other related chemistry problems.

Koen Groenland

**QUANTUM INNOVATION OFFICER AT QUSOFT**

Today's agriculture relies heavily on the use of artificial fertilizer
to grow our crops. Without large-scale use of supplementary nutrients,
it would be problematic to feed our world's huge population. In fact,
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

Pretty much all of the world's ammonia production follows the so-called
Haber-Bosch process, where hydrogen gas (H2) and nitrogen gas (N2) react
together to form ammonia. The process can be implemented in large,
high-yield production lines, but also comes with a major disadvantage:
its staggering energy consumption. This is mainly due to two essential
steps: producing sufficiently pure hydrogen and nitrogen gasses, and
later separating the H2 and N2 molecules into individual atoms. The
latter is especially challenging for N2 due to its strong triple bond.
To achieve this, factories operate at extreme conditions, with high
temperatures (\~400 degrees Celsius) and high pressure, largely driven
by natural gas. As much as [1.8% of the world's CO2
emission](https://royalsociety.org/topics-policy/projects/low-carbon-energy-programme/green-ammonia/) is
caused by factories performing such reactions, consuming around 3-5% of
the world's natural gas production!

Can't this be done more efficiently? In this case, we strongly suspect
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
temperature, this will save a significant percentage of the world's
energy consumption and greenhouse gas emissions. Tom O'Brien, assistant
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

