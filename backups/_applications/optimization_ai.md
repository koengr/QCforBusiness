---
layout: default
title: "Applications in optimization and machine learning"
nav_order: 4
---
 
 
# Applications in optimisation and machine learning 
{: .no_toc }


Reading time: 2 minutes
{: .fs-3 .floatr }

### Contents
{: .no_toc }
{: .mini-header } 

- TOC
{:toc}




TODO: write section! 🡪 See separate document!

**Where should we look for a killer application?**

Well, we simply don’t know! However, some useful technical hints may be:

- As described above, we’d most likely require an *exponential *or
  some *heuristic *speedup. This is much more likely achieved on
  problems where we don’t already know very efficient classical
  algorithms. 

- When reading data is a limiting factor (as in “big data”
  applications), quantum computers appear to be very slow. Getting the
  data into a quantum computer seems to take at least as long as
  processing the data on a much cheaper supercomputer. This holds, for
  example, when searching through a database, but also for
  data-intensive simulations like weather forecasting. 

- Similarly, if the desired output is a large amount of data (such as a
  very large list or table), then a quantum computer is likely not
  efficient. Most quantum algorithms look at a global property of a
  function or dataset that can be encoded in a very small output (like
  Deutsch-Jozsa or Shor’s algorithm when interpreted as finding the
  period of a function). 

- Some people would say that if quantum computers are not “faster”,
  perhaps they might solve a problem “more accurately” (for example,
  they might produce a more reliable forecast). However, when we look at
  speedups, then accuracy is already taken into account: we compare the
  number of steps *asserting the output has a given accuracy. *

- Classical computers are already incredibly fast, and the bottleneck
  for many real-world computational problems is not in a computer’s
  speed. If an application does require a supercomputer today, then it’s
  unlikely that anyone will invest in a quantum computer soon.

