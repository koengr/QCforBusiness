---
layout: default
title: "The impact on cybersecurity"
nav_order: 3
---

# The impact on cybersecurity

In the world of quantum computers, the most convincing exponential
speedup lies in codebreaking. Anyone who wants to understand the impact
of quantum computers, will need to know their basics of cryptography.
Let’s start at the beginning. 

## Cryptography is much more than just secrecy 

Why do we actually use cryptography? Pretty much everyone will
immediately think of:

- **Privacy / confidentiality: **making sure that others cannot read
  your data (especially when messages are sent over a network).

However, there are many more threats that cryptography protects us from.
Most people wouldn’t normally worry about them, but when any of the
following is missing, cybercriminals can cause a lot of harm: 

- **Authentication: **You want to verify that a message really came from
  the entity that claims to send the message. For example, during online
  banking, you want to be 100% sure that you are communicating with your
  bank and nobody else.  
  Another example is when installing a new piece of software. When
  executing the latest Windows update, your computer makes sure to check
  that there is a **‘digital signature’ **that belongs to Microsoft.
  Imagine how unsafe your computer would be if anyone could send fake
  updates!

<!-- -->

- **Integrity: **You want to verify that nobody changed the message
  during transit. Imagine what damage could be caused when your emails
  are maliciously altered before they arrive, or when the commands
  coming from an air traffic control tower are modified. Similarly, any
  software installer confirms that the software wasn’t changed by anyone
  but the original publisher, by verifying a digital signature.

<!-- -->

- **Establishing secret keys: **How do you negotiate a new secret key
  with a brand new webshop that you never visited before? This is a
  seemingly impossible task if bare internet traffic can be read by
  anyone, but modern cryptography has a solution.

There are some others,
like [non-repudiation](https://en.wikipedia.org/wiki/Non-repudiation) and [availability](https://www.fortinet.com/resources/cyberglossary/cia-triad), that
we don’t discuss here. Remember the above bold-faced words, as we will
come across them a lot. 

We hope that this introduction makes the reader aware of the enormous
importance of proper cryptography, and the sheer number of cryptographic
checks that are required for proper functioning of our IT. You would be
surprised how often you use cryptography on a daily basis, through your
laptop, phone, car keys, or smart cards.

## The quantum threat is mainly to public-key cryptography. 

A common misconception, which we see a lot in popular literature, is
that the quantum threat can be summarised as follows. (Both of the
statements below are **incorrect!) **

- A quantum computer will break all of today’s cryptography. 

- A quantum internet is needed to keep our cryptography safe again.

 

To better understand this, let’s first look at what cryptography a
quantum computer will break, and which it won’t. Later, we will look at
the necessity of a quantum internet. 

In line with common cryptography jargon, we will typically have two
parties, Alice and Bob, who want to communicate with each other. We
distinguish two different types of cryptography: the symmetric and the
asymmetric (public key) variants. 

<img src=" {{ site.baseurl }}/media/image19.png" style="width:3.30619in"
alt="Symm and asymmetric cryptography Page 1 copy 2" />

In **symmetric (or private key) cryptography, **we assume that both
Alice and Bob already know some secret key. This could be a password
that they both know, or more commonly, a very long number represented by
(say) 128 bits in their computer memory. Alice can use the key to
encrypt any message using a protocol
like [AES](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard).
Bob can then use the same key to decrypt this message. The details of
how encryption and decryption work are unimportant for our purposes. The
only thing that’s relevant is that our computers can do this very
efficiently, and that it’s considered sufficiently safe: without the
key, nobody could reasonably break this encryption.

<img src=" {{ site.baseurl }}/media/image20.png" style="width:3.15014in"
alt="Symm and asymmetric cryptography Page 3 copy 2 1" />

In asymmetric cryptography, or more often called **public-key
cryptography (PKC)**, each participant has two keys: a public key and
a private key. The public key can be shared with anyone, while
the private key must be kept secret. That’s why we use the suggestive
colours green (save to share) and red (keep private!). If Alice wants to
send an encrypted message to Bob, she uses Bob’s public key to encrypt
the message. If Bob wants to decrypt the message, he uses his private
key. 

The setting with two keys offers more functionality. For example, using
the previous encryption method, Alice could send a secret key to Bob,
which they can then use for symmetric cryptography, which is faster in
practice.

<img src=" {{ site.baseurl }}/media/image21.png" style="width:3.0625in"
alt="Symm and asymmetric cryptography Page 4 copy 2" />

Furthermore, the protocol works in ‘reverse’. Alice can use her private
key to encrypt a message, which then anyone in the world (including Bob)
can decrypt using the corresponding public key. Bob should then be
confident that Alice is the only person in the world who could have
encrypted this message (indeed, something encrypted with the private
key can *only* be decrypted with the public key, and vice versa). This
forms the basis of digital signatures.  

 

<img src=" {{ site.baseurl }}/media/image22.png" style="width:3.04167in"
alt="security google chrome" />

This is precisely what’s used whenever you open a webpage. Your browser
(like Chrome or Firefox) will display that the connection is secure,
which means that, amongst other things, it verified that the digital
signature is valid. This ensures authenticity and integrity. 

It should come somewhat as a surprise that public-key cryptography is
even possible at all! It’s kind of a small wonder that encryption and
decryption with two totally different keys can be made to work, thanks
to some powerful mathematics. For example, I don’t know of any physical
locks that work this way. However, it turns out that the delicate
relationship between the two keys is also a weak spot…

### How good are quantum computers at cracking cryptography? 

In principle,** symmetric-key cryptography** is fairly safe against
quantum hackers. The biggest problems are brute-force attacks, where an
attacker effectively tries every possible secret key. Using a key of 128
bits, the total number of possible keys is 2<sup>128</sup> — that’s an
incomprehensibly large number, much more than the number of atoms in a
human body. 

We know that Grover’s algorithm speeds up brute-force search, by
reducing the number of attempts from 2<sup>128</sup> to its square root,
which is 2<sup>64</sup>. This is something that cryptographers are not
happy about, but considering the slowness and extra overhead that comes
with quantum computers, this doesn’t seem to be a problem in the
foreseeable future. Still, to be on the safe side, it is recommended to
double key lengths, hence to use the same algorithm with 256-bit keys.
Changing this in existing IT infrastructure is relatively
straightforward, although one shouldn’t underestimate the time and costs
for such changes within large organisations.

The situation is completely different with **public-key
cryptography. **The most-used algorithms
today, [RSA ](https://en.wikipedia.org/wiki/RSA_(cryptosystem))and [ECC](https://en.wikipedia.org/wiki/Elliptic-curve_cryptography),
can be straightforwardly broken by a large quantum computer. We
discussed the details of  Shor’s
algorithm [earlier](https://quantumcomputingforbusiness.com/essentials/applications-overview/),
and saw that around [20 million
qubits](https://quantum-journal.org/papers/q-2021-04-15-433/) and around
8 hours are needed to retrieve a secret RSA key. Luckily, there exist
PKC systems that are believed to be safe against quantum computers, and
an obvious way forward is to start using these. We call such
systems **post-quantum cryptography**, and despite the confusing name,
they’re built to work on conventional computers. We discuss the rabbit
hole of migrating to new cryptography [in a different
chapter](https://quantumcomputingforbusiness.com/advanced/strategic-actions/).

Unfortunately, today’s communication is already at risk due to a
practice called **harvest now, decrypt later. **Encrypted messages that
are sent over a network can be intercepted and stored for many years,
until a quantum computer can efficiently decrypt the messages. Even
though we use public-key encryption mainly to establish temporary keys
for symmetric cryptography, a smart attacker could still derive the
necessary intermediate keys. It is inclear at what scales such
large-scale storage of sufficiently detailed internet data is actually
happening, but it seems plausible that security agencies of larger
nations are working on it.

Further reading:

- [Redhat blog on Mosca’s
  theorem](https://www.redhat.com/en/blog/post-quantum-cryptography-introduction),
  which states *when *you should start upgrading if your communication
  needs to remain secret for at least X years.

 

The following table summarizes how our cryptosystems are threatened:

<table>
<colgroup>
<col style="width: 32%" />
<col style="width: 28%" />
<col style="width: 20%" />
<col style="width: 19%" />
</colgroup>
<thead>
<tr class="header">
<th> </th>
<th>Symmetric</th>
<th colspan="2">Public-key</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td> </td>
<td><strong>Today (AES, … )</strong></td>
<td><strong>Today (RSA, ECC)</strong></td>
<td><strong>PQC                      </strong></td>
</tr>
<tr class="even">
<td>Against classical computers</td>
<td>Safe</td>
<td>Safe</td>
<td>Safe</td>
</tr>
<tr class="odd">
<td>Against quantum computers</td>
<td><p>Safe*</p>
<p>*with double key lengths</p></td>
<td><strong>Unsafe</strong></td>
<td>Safe</td>
</tr>
</tbody>
</table>

### Why don’t we switch to symmetric cryptography? 

Public-key cryptography solves a very fundamental problem: how can Alice
and Bob agree on a secret key before they have a means of encryption in
the first place? They cannot just send a new key over the internet
without any form of encryption, because anyone would be able to read
this. This is the fundamental problem of **key distribution**. Let us
look at the functionality offered by the two types of cryptography: 

|   | Symmetric | Public-key                    |
|----|----|----|
| Confidentiality (privacy) | Only with pre-shared keys | ✔ |
| Authentication / Integrity   | Only with pre-shared keys | ✔ |
| Establishing secret keys | **✗** | ✔ |

If only we could somehow give Alice and Bob pre-shared keys in a secure
way, we would resolve most of these problems. Without public-key
cryptography, there are other options:

- Alice and Bob could meet every other week to exchange USB drives with
  secret codes.

- Alice and Bob could both trust a large “key server”. If both share a
  secret key with the key server, they can securely ask the server to
  generate a new secret key that they can use together. 

Still, none of these form an attractive alternative to public-key
cryptography, especially if one considers the sheer number integrity and
authenticity checks we perform every day, and the incredible number of
online entities we potentially want to communicate with. 

## What solutions exist?

TODO: More on PQC, hopefully when new standards are released!

**What about Quantum Key Distribution (QKD)?**

As we saw in a different chapter, Quantum Key Distribution partially
solves the key distribution problem. It requires a quantum network
connection between Alice and Bob, and somewhat expensive quantum devices
to generate and measure photons. When used, Alice and Bob will obtain a
secret key (that can be as long as they like), in a very safe way (in
the sense that nobody listening in on their classical or quantum
communication can possibly find this key). Unlike PKC, this method still
requires pre-shared keys for authentication (because otherwise you can’t
be sure with whom you will share your new secret key). Therefore, it
won’t completely solve the key distribution problem. 

There is even more reason to be careful: many security
authorities [warn](https://www.nsa.gov/Cybersecurity/Quantum-Key-Distribution-QKD-and-Quantum-Cryptography-QC/) [against](https://www.ncsc.gov.uk/whitepaper/quantum-security-technologies) [adopting](https://english.aivd.nl/publications/publications/2022/01/18/prepare-for-the-threat-of-quantumcomputers) [QKD](https://www.bsi.bund.de/EN/Themen/Unternehmen-und-Organisationen/Informationen-und-Empfehlungen/Quantentechnologien-und-Post-Quanten-Kryptografie/Quantenkryptografie/quantenkryptografie.html) today.
Although the theory is very sound, today’s hardware is still in an early
stage. The time to generate secret keys is still relatively long, and it
is very likely that the actual software and hardware contain mistakes
that make them vulnerable to attacks. 

It is somewhat of a pity that QKD is not so mature yet, because it would
be a viable weapon against Harvest Now, Decrypt Later (since harvesting
the pre-shared authentication keys is not a problem). Moreover,
widespread adoption of QKD would make it easier to expand to a
large-scale quantum internet. Nevertheless, since a quantum threat could
be here as soon as the early 2030s, most companies are recommended to
urgently fix their post-quantum cryptography (PQC) first, and
potentially consider QKD as an add-on for additional security later, if
needed. 

 

**What about Quantum Random Number Generators (QRNG)?**

Good random number generators are extremely important in cryptography,
and QRNGs could provide a good alternative to the [hardware random
number
generators ](https://en.wikipedia.org/wiki/Hardware_random_number_generator)that
are widely used today. 

However, all they do is generate random numbers – that doesn’t make any
protocol safe in itself. As a general warning: **products with ‘quantum’
in the name do not automatically protect against Shor’s algorithm!   
**

**What steps should a typical company or government take? **

We dedicate a [separate
chapter](https://www.quantum.amsterdam/part-6-getting-started/) to
that! 

**Conclusion**

It should be clear that cryptography is strongly intertwined with
quantum computing, through Grover’s algorithm, Shor’s algorithm, and
Quantum Key Distribution. Nevertheless, security experts recommend that
there is an obvious way forward:

- Replace current public-key cryptography with new, quantum-safe
  protocols (PQC).

- Double key lengths in symmetric cryptography. 

Especially the first bullet is a major challenge. There are many legacy
systems around on the internet that may not be updated so easily. There
are billions of devices that are all interconnected, so updating one
device will surely cause incompatibilities somewhere else. What’s more,
PQC protocols will surely require more CPU power and more memory than
today’s trusted methods. Companies may need to update the core code of
hundreds or even thousands of applications. And lastly, the new
protocols haven’t been tested as extensively as our conventional
methods, so it is not unlikely that new security issues will be found.
Quantum computers, before they are even built, are already destined to
make the next decade an incredibly complex period for anyone who deals
with cryptography! 

## Further reading

- [The NSA publishes
  recommendations](https://en.wikipedia.org/wiki/Commercial_National_Security_Algorithm_Suite)
  on what which cryptographic algorithms should be used, and sketches a
  concrete timeline about when national security systems should be
  updated.

