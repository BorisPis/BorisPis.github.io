---
title: "ShRing: Networking with Shared Receive Rings"
collection: publications
permalink: /publications/2023-shring
excerpt: ''
date: 2023-07-10
prevenue: "OSDI '23: USENIX Symposium on Operating Systems Design and Implementation"
paperurl: '/files/2023-shring.pdf'
defpaperurl: https://www.usenix.org/conference/osdi23/presentation/pismenny
slides: '/files/2023-shring-slides.pptx'
#poster: '/files/2023-shring-poster.pdf'
#video: 'https://youtu.be/qot-gTh37MU'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Adam Morrison, Dan Tsafrir
#best: 1
#distinguished: 1
#abstract: 1
---
Multicore systems parallelize to accommodate incoming Ethernet traffic,
allocating one receive (Rx) ring with ≥1Ki entries per core by default. This
ring size is sufficient to absorb packet bursts of single-core workloads. But
the combined size of all Rx buffers (pointed to by all Rx rings) can exceed the
size of the last-level cache. We observe that, in this case, NIC and CPU memory
accesses are increasingly served by main memory, which might incur
nonnegligible overheads when scaling to hundreds of incoming gigabits per
second.

To alleviate this problem, we propose "shRing," which shares each Rx ring among
several cores when networking memory bandwidth consumption is high. ShRing thus
adds software synchronization costs, but this overhead is offset by the smaller
memory footprint. We show that, consequently, shRing increases the throughput
of NFV workloads by up to 1.27x, and that it reduces their latency by up to
38x. The substantial latency reduction occurs when shRing shortens the
per-packet processing time to a value smaller than the packet interarrival
time, thereby preventing overload conditions.
