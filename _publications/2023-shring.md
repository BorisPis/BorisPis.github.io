---
title: "ShRing: Networking with Shared Receive Rings"
collection: publications
permalink: /publications/2023-shring
excerpt: ''
date: 2023-07-10
prevenue: "OSDI '23: USENIX Symposium on Operating Systems Design and Implementation"
#paperurl: '/files/2023-shring.pdf'
#defpaperurl: https://dl.acm.org/doi/TODO
#slides: '/files/2023-shring-slides.pdf'
#poster: '/files/2023-shring-poster.pdf'
#video: 'https://youtu.be/qot-gTh37MU'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Adam Morrison, Dan Tsafrir
#best: 1
#distinguished: 1
#abstract: 1
---
Multicore systems employ parallelism to accommodate high incoming Ethernet
traffic, allocating one receive (Rx) ring with 1Ki entries per core, by
default. This ring's size is sufficient to absorb packet bursts of single-core
workloads. But the aggregate memory size of all Rx buffers (pointed to by all
Rx rings) can exceed the LLC size. We observe that such an aggregate size might
incur non-negligible overheads when scaling to hundreds of incoming Gbps, as
memory accesses to Rx buffers (by either NIC or CPU) are increasingly served by
main memory. Rx buffer accesses likewise compete for cache capacity with
concurrent accesses unrelated to networking.

To alleviate this problem, we propose "shRing," which shares a single Rx ring
among several cores when networking memory bandwidth consumption is high.
Helped by minimal firmware changes, we implement shRing on a real NIC. We find
that synchronization costs associated with shRing's sharing are offset by its
smaller memory footprint, which increases the throughput of NFV workloads by up
to 1.27x. ShRing's smaller footprint may additionally prevent overload
conditions, allowing the system to process packets faster than they arrive and
thus reduce the latency by up to 38x.
