---
layout: default
title: "Applications of quantum networks"
nav_order: 2
---

# Applications of quantum networks

If we’re building computers that deal with qubits, superposition and
entanglement, wouldn’t these computers also need some way to send qubits
to each other? This is the dream of the quantum internet: a network that
exchanges quantum-mechanical photons between devices all around the
world, parallel to our well-known ‘classical’ internet. 

There is a bit of a paradox here. On the one hand, a full-blown quantum
internet is very, very far away: a network that reliably transports
actual qubits is arguably harder to realize than a large quantum
computer, as it will build upon the [error
correction](https://en.wikipedia.org/wiki/Quantum_error_correction) technology
that we’re only just figuring out. On the other hand, it is often said
that ‘quantum networks’ have a higher Technology Readiness Level than
computing. That sounds like a contradiction, right?

The main explanation is that there are some applications for ‘imperfect’
quantum networks, in particular in the context of cryptography. 

In that sense, quantum networking applications have always been ‘ahead’
of quantum computing. Already in 1984, long before quantum computers
were seriously considered, researchers Benett and Brassard discovered a
method to securely negotiate a secret key (think of a password) between
two distant parties, based on sending individual photons. Their result
is now famously known as the [BB’84
protocol](https://en.wikipedia.org/wiki/BB84). Similarly, the
commercialization of network technologies has long been ahead of
computing. Early quantum startups like MagiQ Technologies and ID
Quantique were founded around the new millennium, and brought their
first commercial networking products to the market in 2003 and 2004.
This technology, where a quantum network is used to generate a secret
key at two endpoints, is called Quantum Key Distribution (QKD) – an
application that we will address in much more detail below.

## The promises of the quantum internet

There is a long list of arguments why we should be excited about the
quantum internet. Here is a list of the applications that we hear most
frequently:

- **Clustering quantum computers:** By connecting multiple smaller
  computers, one might build a much larger computer which has more
  combined memory and can tackle larger problems. 

- **Securing your classical communication. **The main contender here
  is[ Quantum Key Distribution
  (QKD)](https://en.wikipedia.org/wiki/Quantum_key_distribution),
  sometimes dubbed the “unhackable” network. This allows two distant
  users to create a secret key (think of a password) that they can later
  use for further cryptographic applications.

<!-- -->

- **“Blind computing”: Encrypting your data while still allowing someone
  else to process it. **What if you hire an Amazon cloud computer to do
  calculations on your data, but you don’t want Amazon to actually see
  your data? It turns out that you can make quantum computers do their
  computations even while data remains encrypted, with some caveats.  
  Similarly, one could use ‘encrypted’ software to solve someone else’s
  problem without them discovering this algorithm. Such applications
  often go by the name of blind computing or private computing. 

  - [A scientific (hard!) overview of blind computing
    applications. ](https://www.nature.com/articles/s41534-017-0025-3)

<!-- -->

- **Position verification: **Can you prove that you are currently at a
  given location, in a way that cannot be spoofed? 

  - [A short introductory video
    \[3:23\]](https://www.youtube.com/watch?v=afw0EXQ-4cI&ab_channel=M%C3%A1t%C3%A9Galambos)

<!-- -->

- **Protocols with multiple parties, where not every participant can be
  trusted**, such as [leader
  election](https://en.wikipedia.org/wiki/Leader_election) or [Byzantine
  agreement](https://en.wikipedia.org/wiki/Quantum_Byzantine_agreement).
  You can find many more in the [Quantum Protocol
  Zoo. ](https://wiki.veriqloud.fr/index.php?title=Protocol_Library)

<!-- -->

- **Make quantum sensors more effective**. There exist proposals to
  combine different telescopes or gravitational wave detectors, and
  plans to synchronize quantum clocks. 

  - [A scientific (hard!) overview of distributed quantum
    sensing](https://iopscience.iop.org/article/10.1088/2058-9565/abd4c3)

Much more about the various applications can be found in this[ online
Quantum Internet
magazine](https://tu-delft.foleon.com/tu-delft/quantum-internet/cover/) by
TU Delft, or as[ listed by the Quantum Internet
Alliance](https://quantuminternetalliance.org/quantum-internet-use-cases/).

## How useful is the quantum internet in practice? 

Admittedly, many applications of the quantum internet will depend on how
much we will use quantum computers. If quantum computers become
widespread in the future, then communication between them also seems to
be extremely worthwhile. On the other hand, our current outlook of
quantum computers focuses on special-purpose devices that are used to
solve isolated problems. It is not immediately clear what the value of
exchanging quantum data is.

There is a clear road map to build a reliable quantum internet in the
future (involving fascinating tricks like [entanglement
distillation](https://en.wikipedia.org/wiki/Entanglement_distillation) and [teleportation](https://en.wikipedia.org/wiki/Quantum_teleportation)),
but this would require multiple error-corrected quantum computers by
itself! For that reason, in this guide, we’re not yet looking ahead at
applications like clustering computers, multi-party computations,
private computing, or making sensors more effective. Regarding clustered
quantum computers**, **we frequently hear arguments that one can make a
‘bigger’ quantum computer by connecting individual ones. It seems to me
that building these computers right next to each other (and calling it a
single computer) is much more effective than transporting fragile
quantum data over large distances – clustering seems mainly viable on
extremely small networks.

In the foreseeable future, the first interesting applications are those
that work over a “noisy” connection, and transport just one qubit at a
time (or perhaps a handful of them). For practical interest, **Quantum
Key Distribution (QKD)** is by far the most interesting application.

##  The case for QKD

To fully understand QKD, we will need to have a bit more background
about cryptography, especially the “key distribution problem”. For a
full account, we [recommend first reading the chapter on
cryptography](https://quantumcomputingforbusiness.com/applications/cybersecurity/).
In short: we’re wondering how Alice can agree on a secret key with her
distant friend Bob, in a world where everyone can read plain data sent
over the internet. Surely they can’t just send their secrets or
passwords over to each other, without having any encryption in the first
place! This problem is commonly solved using *public key
cryptography* (which we know will be revamped in the following years).
If you really don’t trust public-key cryptography, the main alternative
is to physically transport a usb stick by a trusted courier. 

Compared to conventional cryptography, the unique selling point of QKD
is that it is fundamentally impossible for cybercriminals to obtain the
secret key as it is being distributed. As long as our understanding of
quantum mechanics is correct (and we’re quite convinced it is, as it’s
arguably the most [well-test theory in
science](https://www.forbes.com/sites/chadorzel/2015/07/20/three-experiments-that-show-quantum-physics-is-real/)),
no amount of computational power or mathematical breakthroughs will let
an attacker gain information about the key. Of course, this assumes that
the protocol is executed precisely as prescribed, and there are no other
vulnerabilities in the actual hardware or software used. 

This is fundamentally different from today’s approach of public key
cryptography, which must rely on certain mathematical assumptions. We
know for sure that, with sufficient computational power, these codes can
be broken, but we argue that this takes such an awfully long time that
nobody will bother (except for bragging rights and [prize
money](https://en.wikipedia.org/wiki/RSA_Factoring_Challenge)[^57]).
Still, such statements about computation times are based on assumptions,
and our trust is purely based on our experience that cryptographers have
not been able to break them yet. In fact, well-regarded cryptosystems do
get broken from time to time, such
as [SIKE](https://arstechnica.com/information-technology/2022/08/sike-once-a-post-quantum-encryption-contender-is-koed-in-nist-smackdown/),
which was in the race to become a new NIST standard. 

That said, although QKD is “unhackable” in theory, the actual
hardware *and *software are equally likely to contain vulnerabilities.
Contrary to well-trusted public-key cryptography, no QKD system has
received proper certification and accreditation, and a significant
fraction of historical
products [have](https://opg.optica.org/oe/fulltext.cfm?uri=oe-15-15-9388&id=139925) [been](https://iopscience.iop.org/article/10.1088/1367-2630/11/6/065001/meta) [hacked](https://arxiv.org/abs/1008.4593). 

QKD has the downside that it requires specialised hardware, although it
is much less demanding than other quantum internet applications we
mentioned. It can already prove useful on a basic point-to-point network
with just two connected parties, of which one should send photons, and
the other measure them. This is orders of magnitude less complex than
building a fully-featured internet. Moreover, the qubits need only be
sent and measured one at a time: no quantum memory or extensive quantum
computations are needed. There have already been several demonstrations
that use standard telecom fiber (the stuff that’s already in the
ground), or satellite-based systems that communicate through air. QKD
hardware is fancy and expensive, but not completely out of reach. 

The major downside of QKD is that it has no way to confirm who the
person on the other end of the line is. Some form of authentication is
still needed – which is mostly done with secret keys that should already
be present in the first place! This makes QKD just a partial solution to
the key distribution problem. 

 

[^57]: See <https://en.wikipedia.org/wiki/RSA_Factoring_Challenge>.

### Further reading about QKD

- A video explanation of QKD
  for [laymen](https://www.youtube.com/watch?v=V3WzH2up7Os&ab_channel=ImprobableMatter) or [experts](https://www.youtube.com/watch?v=2ExG7UJgfmQ&ab_channel=ArturEkert).

- Companies
  like [Toshiba](https://www.toshiba.eu/quantum/products/quantum-key-distribution/long-distance-qkd-system-ld/) and [ID
  Quantique](https://www.idquantique.com/quantum-safe-security/products/#quantum_key_distribution) offer
  commercial QKD systems for distances of around 100 km. 

- Chinese scientists achieve [QKD through
  satellites](https://www.scientificamerican.com/article/china-reaches-new-milestone-in-space-based-quantum-communications/) over
  1000 km. 

- Nature commentary [why practical long-range QKD is still out of
  reach](https://www.nature.com/articles/s41534-022-00613-4). 

### What do experts say? 

Cryptographers that have been working on securing classical computers
are typically sceptical about QKD. In fact, all security authorities
that we are aware of will advise against the use of QKD at this current
point in time. They find the use of additional, uncertified hardware too
large of a security risk, and stress that there is a better solution
that works on conventional computers: **post-quantum cryptography
(PQC)**. From their perspective, PQC offers all the required
functionalities, and is currently more practical to test, certify and
implement. 

Be careful not to confuse the abbreviations PQC and QKD. QKD is about
communication with a fancy quantum network. PQC runs on conventional
hardware. You may call both of them ‘quantum-safe’ cryptography, as they
should both resist attacks from a lage-scale quantum computer.

**A discussion between physicists and cryptographers.**

A fair argument in favour of QKD, stems from the ‘[harvest now, decrypt
later](https://www.quantum.amsterdam/part-8-the-impact-on-cybersecurity/)’
attacks that could be done over today’s internet. These would imply that
even the privacy of today’s messages is compromised. This could be a
convincing reason for organisations to rapidly switch to QKD for their
most sensitive data. Still, for those who are willing to go the extra
mile for their privacy, it might be more worthwhile to look at more
mature and readily available solutions. For example, there exist
certified solutions that rely on symmetric encryption with trusted
couriers. 

**See also:**

- [Compumatica offers symmetric encryption with keys transported on
  SD-cards.  ](https://www.compumatica.com/products/products/cryptoguard/)

- [TNO designed a ‘quantum-safe proxy’ as add-on to existing
  cryptography. ](https://www.tno.nl/en/digital/digital-innovations/trusted-ict/cyber-security-through-quantum-safe/)

- StackOverflow question: [“Why does the NSA find QKD
  impractical”](https://crypto.stackexchange.com/questions/93830/why-quantum-key-distribution-qkd-is-impractical)?

 

What’s left is a very niche use-case for the most forward-thinking
organisations that deal with extreme security requirements. It is
somewhat of a pity that QKD is not so mature yet today, now that many
organisations will start a migration to quantum-safe cryptography. A
widespread adoption of QKD would make it easier to expand to a
large-scale quantum internet in the future. Nevertheless, since a
quantum threat could be here as soon as the early 2030s, most companies
are recommended to urgently migrate to post-quantum cryptography (PQC)
first, and potentially consider QKD as an add-on for additional security
later, if needed. 

 

### Conclusion

In conclusion, most applications of a quantum internet will not be
immediately relevant in the foreseeable future, with an exception for
QKD. And even QKD might not be the killer applications that many
investors are hoping for – it most definitely shouldn’t be called
“unhackable”. 

Still, it seems unfair to us to dismiss a quantum internet because it
would be ‘too technologically challenging’ or ‘too expensive’. These
arguments are correct today, but perhaps naive on a scale of several
decades. Would anyone from the 70’s have believed that today, more than
half of the world population is streaming videos on a mobile phone for
just a few dollars per month? Who knows what the quantum internet will
look like 50 years from now. 

