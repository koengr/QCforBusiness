---
layout: default
title: "8. Applications of quantum networks"
nav_order: 3
---
 
 
# Applications of quantum networks
{: .no_toc }


Reading time: 9 minutes
{: .fs-3 .floatr }

### Contents
{: .no_toc }
{: .mini-header } 

- TOC
{:toc}




If we’re building computers that deal with qubits, superposition, and entanglement, wouldn’t these computers also need some way to send qubits to each other? This is the dream of the quantum internet: a network parallel to our well-known classical internet that allows the transmission of qubits.

There is a bit of a paradox here. On the one hand, a full-blown quantum internet that stretches across the globe is very, very far away – it will require quantum repeaters to bridge longer distances, purification mechanisms to repair imperfections, and many more technologies that we’re only just figuring out. On the other hand, it is often said that quantum networks have a higher Technology Readiness Level than computing. That sounds like a contradiction, right?

The main explanation is that there are some applications for small-scale ‘imperfect’ quantum networks, particularly in the context of cryptography. 

In a sense, quantum networking applications have always been ahead of quantum computing. Already in 1984, long before quantum computers were seriously considered, quantum pioneers Charles Bennett and Gilles Brassard discovered a method to securely negotiate a secret key (think of a password) between two distant parties based on sending individual photons. Their result is now famously known as the [BB'84 protocol](https://en.wikipedia.org/wiki/BB84). Similarly, the commercialisation of network technologies has long been ahead of computing. Early quantum startups like MagiQ Technologies and ID Quantique were founded around the start of this century, and their first commercial networking products were brought to the market in 2003 and 2004. This technology, where a quantum network is used to generate a secret key at two endpoints, is called Quantum Key Distribution (QKD) – an application that we will address in much more detail below.

## The promises of the quantum internet

There is a long list of arguments why we should be excited about the quantum internet. Here are some of the applications that we hear most frequently:

- **Clustering quantum computers:** By connecting multiple smaller computers, one might build a much larger computer with more combined memory, allowing it to tackle more complex problems.  

- **Securing classical communication. **The main contender here is [Quantum Key Distribution (QKD)](https://en.wikipedia.org/wiki/Quantum_key_distribution), sometimes dubbed the ‘unhackable’ network. This allows two distant users to create a secret key (think of a password) that can be used in further cryptographic applications.

- **‘Blind computing’: Encrypting data while still allowing someone else to process it. **What if you hire an Amazon cloud computer to do calculations on your data, but you don’t want Amazon to actually see the data itself? It turns out that you can make quantum computers do their computations even while the data remains encrypted, with some caveats. Similarly, one could use ‘encrypted’ software to solve someone else’s problem without them discovering this algorithm. Such applications often go by the name of blind computing or private computing. 

- **Position verification: **Can you prove that you are currently at a given location in a way that cannot be spoofed? 

- **Protocols with multiple parties, where not every participant can be trusted**, such as  [leader election](https://en.wikipedia.org/wiki/Leader_election) or [Byzantine agreement](https://en.wikipedia.org/wiki/Quantum_Byzantine_agreement). You can find many more in the [Quantum Protocol Zoo](https://wiki.veriqloud.fr/index.php?title=Protocol_Library).

- **Make quantum sensors more effective**. There exist proposals to combine different telescopes or gravitational wave detectors, and plans to synchronise quantum clocks. 

## How useful is the quantum internet in practice? 

The impact of many quantum network applications will depend on how much we will use quantum computers. If quantum computers become widespread in the future, then communication between them also seems to be extremely worthwhile. On the other hand, our current outlook of quantum computers focuses on special-purpose devices used to solve isolated problems. In the latter scenario, the value of exchanging quantum data is not immediately clear.

There is an intriguing road map to build a reliable quantum internet in the future (involving fascinating tricks like [entanglement distillation](https://en.wikipedia.org/wiki/Entanglement_distillation) and [teleportation](https://en.wikipedia.org/wiki/Quantum_teleportation)), but this would require multiple error-corrected quantum computers by itself! Therefore, in this book, we’re not yet ready to look ahead at applications like clustering computers, multi-party computations, private computing, or making sensors more effective. Regarding clustered quantum computers**, **we frequently hear arguments that one can make a bigger quantum computer by connecting individual ones, giving us access to larger numbers of qubits in a single calculation. It seems that building these computers right next to each other (and calling it a single computer) is much more effective than transporting fragile quantum data over large distances – clustering seems useful in extremely small networks.

In the foreseeable future, the first interesting applications are those that work over a ‘noisy’ connection and transport just one qubit at a time (or perhaps a handful of them). For practical interest, **Quantum Key Distribution (QKD)** is by far the most interesting application.

## The case for QKD

To fully understand QKD, we require a bit more background about cryptography, especially the key distribution. For a full account, we recommend first reading the [chapter on cryptography](https://introtoquantum.org/applications/cybersecurity/). In short, we’re wondering how Alice can agree on a secret key with her distant friend Bob in a world where everyone can read plain data sent over the internet. Surely, they can’t just send their secrets or passwords over to each other without having any encryption in the first place! This problem is commonly solved using *public key cryptography* (which we know will be revamped in the following years). If you really don’t trust public key cryptography, the main alternative is to physically transport a USB stick by a trusted courier. 

Compared to conventional cryptography, the unique selling point of QKD is that it is fundamentally impossible for cybercriminals to obtain the secret key as it is being distributed. As long as our understanding of quantum mechanics is correct (and we’re convinced it is, as it’s arguably the [most well-tested theory in science](https://www.forbes.com/sites/chadorzel/2015/07/20/three-experiments-that-show-quantum-physics-is-real/)), no amount of computational power or mathematical breakthroughs will let an attacker gain information about the key. Of course, this assumes that the protocol is executed precisely as prescribed and that there are no other vulnerabilities in the actual hardware or software. 

This fundamentally differs from today’s approach to public key cryptography, which must rely on certain mathematical assumptions. We know for sure that, with sufficient computational power, these codes can be broken, but we argue that this takes such a painfully long time that nobody will bother. Still, such statements about computation times are based on assumptions, and our trust derives from the empirical evidence that our smartest cryptographers have not found any weaknesses yet. In fact, well-regarded cryptosystems do get broken from time to time.

That said, although QKD is ‘unhackable’ in theory, the actual hardware *and *software are likely to contain vulnerabilities. Contrary to well-trusted public key cryptography, no QKD system has received proper certification and accreditation, and a significant fraction of historical products [have](https://opg.optica.org/oe/fulltext.cfm?uri=oe-15-15-9388&id=139925) [been](https://iopscience.iop.org/article/10.1088/1367-2630/11/6/065001/meta) [hacked](https://arxiv.org/abs/1008.4593). 

QKD has the downside that it requires specialised hardware, although it is much less demanding than other quantum internet applications we mentioned. It can already be practical with a basic point-to-point network with just two connected parties, with one party limited to sending photons and the other limited to just measuring them. Moreover, the qubits need only be sent and measured one at a time, so no quantum memory or extensive quantum computations are needed. There have already been several demonstrations that use standard telecom fibre (the stuff that’s already in the ground) or satellite-based systems that communicate through air. QKD hardware is fancy and expensive but not completely out of reach. 

The fundamental downside of QKD is that it features no intrinsic way to confirm who the person on the other end of the line is. Some form of authentication is still needed – which is done with secret keys that should already be present in the first place! This makes QKD just a partial solution to the key distribution problem: it’s mostly a key *extension* protocol, creating arbitrary amounts of key material based on a small initial key.

### What do experts say? 
{: .no_toc }

Cybersecurity experts (indeed, the people who have been diligently keeping our classical computers safe for decades) are typically sceptical about QKD. In fact, all major security authorities that we are aware of currently advise against the use of QKD. They find the use of additional, uncertified hardware too large of a security risk and stress that there is a better solution that works on conventional computers: post-quantum cryptography (PQC). From their perspective, PQC offers all the required functionalities, and is currently more practical to test, certify and implement. 

Be careful not to confuse the abbreviations PQC and QKD. QKD is about communication with a fancy quantum network. PQC runs on conventional hardware. You may call both of them ‘quantum-safe’ cryptography, as they should both resist attacks from a large-scale quantum computer.

A fair argument in favour of QKD stems from the [harvest now, decrypt later](https://www.quantum.amsterdam/part-8-the-impact-on-cybersecurity/) attacks that could be done today. These imply that even the privacy of today’s messages is at risk, which could be an argument for organisations to rapidly switch to QKD to protect their most sensitive data. Still, for those willing to go the extra mile for their privacy, looking at more mature and readily available solutions might be more worthwhile. For example, there exist certified solutions that rely on symmetric encryption with trusted couriers.  

What’s left is a niche use case for the most forward-thinking organisations that deal with fierce security requirements. It is a pity that QKD is not so mature today, as many organisations will start a migration to quantum-safe cryptography soon. Widespread adoption of QKD would likely lower the costs of quantum networks and make it easier to expand to a large-scale quantum internet in the future. Nevertheless, since a quantum threat could be here as soon as the early 2030s, we stick with the recommendation to migrate to post-quantum cryptography first and to consider QKD as an add-on for additional security later, if needed. 

## Conclusion

In conclusion, most applications of a quantum internet will not be immediately relevant in the foreseeable future, with an exception for QKD. And even QKD might not be the killer applications that many investors are hoping for – it most definitely shouldn't be called ‘unhackable’. 

Still, it seems unfair to dismiss a quantum internet because it would be ‘too technologically challenging’ or ‘too expensive’. These arguments are correct today but could be naive on a scale of several decades. Would anyone from the 1970s have believed that today, almost everyone on the globe is streaming videos on a mobile phone for just a few dollars per month? Who knows what the quantum internet will look like thirty years from now? 

## Further reading

- Much more about the various quantum network applications can be found in an [online Quantum Internet magazine](https://tu-delft.foleon.com/tu-delft/quantum-internet/cover/) by TU Delft or on the website of the [Quantum Internet Alliance](https://quantuminternetalliance.org/quantum-internet-use-cases/).

- A video explanation of QKD for [laymen](https://www.youtube.com/watch?v=V3WzH2up7Os&ab_channel=ImprobableMatter) or [experts](https://www.youtube.com/watch?v=2ExG7UJgfmQ&ab_channel=ArturEkert).

- A video explanation of [Quantum Position Verification](https://www.youtube.com/watch?v=afw0EXQ-4cI).

- A nature commentary on [why practical long-range QKD is still out of reach](https://www.nature.com/articles/s41534-022-00613-4). 

