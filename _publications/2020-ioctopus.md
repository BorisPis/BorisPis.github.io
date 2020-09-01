---
title: "IOctopus: Outsmarting Nonuniform DMA"
collection: publications
permalink: /publications/2020-ioctopus
excerpt: **awarded Best paper**
date: 2020-03-18
venue: "ASPLOS '20: ACM International Conference on Architectural Support for Languages and Operating Systems"
paperurl: 'https://dl.acm.org/doi/abs/10.1145/3373376.3378509'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Igor Smolyar, Alex Markuze, Boris Pismenny, Haggai Eran, Gerd Zellweger, Austin Bolen, Liran Liss, Adam Morrison, Dan Tsafrir
---

In a multi-CPU server, memory modules are local to the CPU to which they are
connected, forming a nonuniform memory access (NUMA) architecture. Because
non-local accesses are slower than local accesses, the NUMA architecture might
degrade application performance. Similar slowdowns occur when an I/O device
issues nonuniform DMA (NUDMA) operations, as the device is connected to memory
via a single CPU.  NUDMA effects therefore degrade application performance
similarly to NUMA effects.

We observe that the similarity is not inherent but rather a product of
disregarding the intrinsic differences between I/O and CPU memory accesses.
Whereas NUMA effects are inevitable, we show that NUDMA effects can and should
be eliminated. We present IOctopus, a device architecture that makes NUDMA
impossible by unifying multiple physical PCIe functions—one per CPU—in manner
that makes them appear as one, both to the system software and externally to
the server. IOctopus requires only a modest change to the device driver and
firmware. We implement it on existing hardware and demonstrate that it improves
throughput and latency by as much as 2.7× and 1.28×, respectively, while
ridding developers from the need to combat (what appeared to be) an unavoidable
type of overhead.
