---
layout: default
title: "Four myths about quantum computing"
nav_order: 6
---
 
 
# Four myths about quantum computing
{: .no_toc }


Reading time: 10 minutes
{: .fs-3 .floatr }

### Contents
{: .no_toc }
{: .mini-header } 

- TOC
{:toc}




This chapter relies on a bit of quantum physics jargon. See the
[Introduction to the quantum
world](https://quantumcomputingforbusiness.com/essentials/quantum/) for
a quick introduction.

## Myth 1: Quantum computers find all solutions at once

This myth is likely the most technical, and builds on a
misinterpretation of the concept of superposition. A single qubit can be
in two states at the same time (0 and 1), two qubits can represent four
states (00, 01, 10, 11), and three qubits are potentially in eight
unique configurations simultaneously. As we increase the number of
qubits, this number of coexisting states scales exponentially!

This means that a mere 1000 qubits can effectively ‘store’ \\(2^{1000}\\)
unique values, all at the same time. That’s an incomprehensibly large
number, much more than there are atoms in the visible universe. Even the
fastest computers in the world couldn’t loop through all these states in
a lifetime. Each of these states can be interpreted like a file on a
computer, be it an Excel spreadsheet, a web page, a CAD drawing, or
whatever kind of data we choose to work with.

A smart computer scientist can also devise a way to make 1000 bits
represent ‘solutions’ to some problem. For example, imagine that we want
to find an optimal aeroplane wing that generates incredible lift while
requiring as few materials as possible. Using quantum superposition, we
might represent \\(2^{1000}\\) such wings all at once.

We picked the example of aeroplane wings because simulating their
aerodynamic properties requires a pretty hefty computation. Let’s assume
that we have written such a computer program that accurately simulates
any wing, and call that program \\(f\\). It will output 1 if the wing works
well (according to whatever metric), and 0 otherwise. Surely, the
program takes a very large number of computation steps, which we’ll call
T. The program will need some input, denoted by \\(x\\), which is a 1000-bit
description of all the relevant properties of a hypothetical aeroplane
wing. In other words, the compute program computes \\(f(x) = 1\\) if \\(x\\) is
a fantastic wing, and \\(f(x) = 0\\) if it’s rubbish.

Now, a quantum computer should be able to execute any classical
function, right? We should be able to run \\(f\\) on a quantum computer, but
now we have the unique feature that the 1000-qubit input can represent a
humongous number of potential aeroplane wings at the same time! By doing
a mere T computational steps, we can check the properties of \\(2^{1000}\\)
solutions!

If this actually worked, quantum computers would have an astonishing
power. They could straightforwardly find mathematical proofs that humans
haven’t been able to solve in centuries, simply by trying all possible
proofs in parallel. They would rapidly produce the perfect train and bus
schedules, discover new drugs and straightforwardly hack encryption
systems. They would solve problems in the [complexity class
NP](https://en.wikipedia.org/wiki/NP_(complexity)), which is widely
believed to be impossible with machines in our universe, owing to the
famous P ≠ NP conjecture.

So, where’s the catch? For those who read the introduction to quantum
physics, we shouldn’t forget about the postulate of quantum measurement.
The output of the computation would be a *superposition* over \\(2^{1000}\\)
outcomes. If we want to learn anything about this output, we’d perform a
quantum measurement that collapses this superposition. Instead of
looking at \\(2^{1000}\\) different solutions simultaneously, we get to see
only one outcome – corresponding to the performance of just a random
aeroplane wing. In this case, there is no advantage compared to a
classical computer because we could’ve just as well picked a random wing
at first, and then spent the same T steps on a (much faster) classical
machine.

Although this ‘quantum parallelism’ is too good to be true, quantum
computers can use the above idea to some lesser extent. Using [Grover’s
algorithm](https://en.wikipedia.org/wiki/Grover%27s_algorithm), we can
find desirable solutions (the \\(x\\) for which \\(f(x) = 1\\)) in roughly the
*square root* of the number of values that \\(x\\) can take. In the above
example, the number of required steps is reduced to
\\(\sqrt{2^{1000}}\ T = 2^{500}\ T\\). This is an incredible reduction, but
we’re still looking at a number of steps larger than the number of atoms
in the universe – finding solutions with this brute-force method remains
far from efficient.

## Myth 2: Qubits can store much more data than the same number of classical bits. 

This myth is very similar to the previous one: can’t N qubits represent
\\(2^{N}\\) different numbers at the same time? Or aren’t they perhaps even
more powerful, because for each of the \\(2^{N}\\) different numbers,
there’s a complex number, which can have as many decimal digits as we
like?

Again, by the rules of quantum measurement, this is too good to be true.
It’s impossible to store much information in a qubit because it
collapses to a classical 0 or 1 when we measure it. The problem is
really in *retrieving* the information, where we have very limited
capabilities. For the same reason, when sending a classical message over
a long distance, there’s little value in using qubits as information
carriers.

As a side note, there is a fascinating related protocol called
[‘superdense coding’](https://en.wikipedia.org/wiki/Superdense_coding)
that you may like to look up out of theoretical interest. Also, when
your data itself represents something quantum (for example, the state of
electrons in a molecule), then storing this data in qubits does have a
potentially huge advantage.

## Myth 3: Entanglement allows you to send information faster than light or to influence objects at a distance

Entanglement is an incredibly confusing phenomenon. In particular, our
most common interpretation of quantum mechanics states that whenever we
measure one qubit, the state of another distant qubit can drastically
change. Whilst this picture is helpful for physicists when performing
computations, it tricks our intuition.

Imagine that, in the faraway future, we want to protect our solar system
against an alien invasion. We installed sentinels on faraway outposts,
which should signal Earth of any approaching dangers. Alice is one of
these noble guards stationed at a remote asteroid in the icy Kuiper
Belt. She brought with her a qubit labelled A, which is entangled with
another qubit B that's safely kept on earth by her colleague Bob. Whilst
it takes light signals around 5 hours to travel between them, isn't
there a way for Alice to alarm Bob any faster, possibly by doing some
special operations on her qubit? Perhaps she could even give some clues
about the type of looming threat?

Unfortunately, Alice cannot remotely change any *measurable quantity* of
Bob's qubit. Bob's measurements will always have the same outcome
probabilities, no matter what Alice does to her qubit. Using more qubits
or employing different quantum objects won't help either. Fundamentally,
there is no way to signal any information faster than the speed of
light.

There is a subtle difference between ‘changing measurable quantities’
and ‘knowing something’ about the state of a particle. To illustrate,
assume that we start with a particular entangled state: measuring qubits
A and B will result either in both qubits being ‘0’ or both qubits being
‘1’, let's say with 50% probability each. Measuring something like A=
‘0’ and B= ‘1’ is impossible.

When Alice measures her qubit and reads the outcome ‘0’, she immediately
knows the outcome of a future measurement made by Bob: she knows this
will be ‘0’ with 100% probability. However, this knowledge is not
accessible to Bob. He doesn't even know whether Alice measured or not!
Even if they agreed in advance that Alice would measure at a set time,
Bob doesn't know her outcome. From his perspective, ‘0’ or ‘1’ are still
equally likely.

Something interesting happens when Alice sends a message to Bob to
inform him that her measurement returned ‘0’. With this updated
knowledge, Bob suddenly knows precisely what the state of his qubit is:
it must have collapsed to ‘0’, and he can perfectly predict the outcome
of a subsequent measurement. In a way, this did indeed change the state
of the qubit from Bob's perspective, but it was only possible after some
(classical) communication took place between Alice to Bob, a process
that is limited by the speed of light.

What is quantum entanglement good for, then? Some potential applications
include:

- Creating certifiably secure encryption keys at remote locations.

- Creating certifiable randomness.

- Forming connections between separate quantum computers, allowing them
  to send quantum data to each other using
  [teleportation](https://en.wikipedia.org/wiki/Quantum_teleportation).
  For this to work, devices also need to transfer some classical data,
  so qubit transmission is never faster than the speed of light.
  Teleportation is an intriguing method to scale up quantum computers
  when a limited number of qubits can fit on a single chip or within a
  single fridge.

## Myth 4: Quantum computers are always ten years away.

This statement is a playful reference to the situation around nuclear
fusion, where predictions of its realisation being just 30 years in the
future have repeatedly been postponed. Scientists have been working on
fusion for decades, but it’s still far from a mature energy source.

Similarly, I’ve heard several overly optimistic claims about quantum
computers being made in the past ten years, often claiming that quantum
computers are somewhere between three to ten years away. An article by
TechCrunch[^43] boldly paraphrases Dario Gil (IBM) and Chad Rigetti
(founder of Rigetti Computing) saying that ‘[the moment that a quantum
computer will be able to perform operations better than a classical
computer is only three years
away](https://techcrunch.com/2018/09/07/the-reality-of-quantum-computing-could-be-just-three-years-away/?guccounter=1)’,
whilst this article was published back in 2018. For reference, the
127-qubit Eagle chip was announced by IBM at the end of 2021, but even
several years later, it’s still primarily used for testing and
education. In 2019, consulting firm Gartner published ‘The CIO's Guide
to Quantum Computing’, which indicates that 100—200 qubits are
sufficient for ‘key potential applications’ in chemistry. They also
predicted that ‘by 2023, 20% of organisations will be budgeting for
quantum computing projects’. Clearly, these predictions were overly
optimistic.

Similarly, Microsoft made claims in 2018 that their cloud platform Azure
would feature quantum computing in 5 years[^44], which is technically
true. However, they have repeatedly hinted to do this with
fault-tolerant topological qubits, which still remain elusive. Startup
PsiQuantum famously claimed to have a million photonic qubits by
2025[^45], and consultants at BCG advised that quantum computers
‘generate business value’ in the same year[^46]. Again, it remains to be
seen if this holds true.

Luckily, if you’re reading this book, you must have noticed that not all
experts share the same vision. Most scientists have warned for a long
time that quantum computing is a long-term effort.

Nevertheless, the thesis that ‘quantum computing is always X years away’
is hard to defend, thanks to convincing evidence that we are steadily
progressing towards a clear goal. Every year, quantum hardware sees
major improvements in the number of qubits, their stability, and the
level of control that is demonstrated. Most experts even expect an
exponential scaling of the number of qubits, similar to Moore’s Law, and
manufacturers have clear roadmaps that underline these predictions.
Moreover, theorists have set clear targets for when the hardware is good
enough—and we’d sooner see the requirements drop with new breakthroughs
rather than become more stringent. Building a quantum computer is a long
marathon, and it’s impossible to predict when they will become
commercially relevant, but the rapid rate of progress is undeniable.

[^43]: Shieber, Jonathan. ‘The Reality of Quantum Computing Could Be
    Just Three Years Away.’ TechCrunch, September 7, 2018.
    <https://techcrunch.com/2018/09/07/the-reality-of-quantum-computing-could-be-just-three-years-away/>.

[^44]: Saran, Cliff. ‘Microsoft Predicts Five-Year Wait for Quantum
    Computing in Azure.’ ComputerWeekly.com, May 9, 2018.
    <https://www.computerweekly.com/news/252440763/Microsoft-predicts-five-year-wait-for-quantum-computing-in-Azure>.

[^45]: Cookson, C. (2021) ‘PsiQuantum expects commercial quantum
    computer by 2025’, 13 March. Available at:
    <https://www.ft.com/content/a5af3039-abbf-4b25-92e2-c40e5957c8cd>
    (Accessed: 26 September 2024).

[^46]: Matt Langione, Jean-François Bobier, Zheng Cui, Cassia
    Naudet-Baulieu, Amit Kumar, and Antoine Gourévitch. ‘Quantum
    Computing Is Becoming Business Ready.’ BCG Global, April 27, 2023.
    <https://www.bcg.com/publications/2023/enterprise-grade-quantum-computing-almost-ready>.

## Further reading

- (Youtube) [Veritasium explains
  Entanglement](https://www.youtube.com/watch?v=ZuvK-od647c)

- (Youtube, technical!) [Minute Physics explains
  Teleportation](https://www.youtube.com/watch?v=DxQK1WDYI_k)

- Chris Ferrie debunks more myths in his free book ‘[What you shouldn’t
  know about Quantum Computers](https://arxiv.org/abs/2405.15838)‘

- Scott Aaronson shares a transcript of a public talk, explaining why he
  [is optimistic about the steady progress towards large-scale quantum
  computers](https://scottaaronson.blog/?p=8329).

