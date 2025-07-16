---
title: "Disentangling the dual role of NIC receive rings"
collection: publications
permalink: /publications/2025-rxbisect
excerpt: ''
date: 2025-07-07
prevenue: "OSDI '25: USENIX Symposium on Operating Systems Design and Implementation"
paperurl: '/files/2025-rxbisect.pdf'
defpaperurl: https://www.usenix.org/conference/osdi25/presentation/pismenny
slides: '/files/2025-rxbisect-slides.pptx'
#poster: '/files/2025-rxbisect-poster.pdf'
#video: 'https://youtu.be/qot-gTh37MU'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Adam Morrison, Dan Tsafrir
#best: 1
#distinguished: 1
#abstract: 1
---
CPUs parallelize packet processing across cores via per-core
receive (Rx) rings, which are typically sized to absorb bursts
with >=1Ki entries by default. The combined I/O working
set (packet buffers pointed to by all Rx rings) easily exceeds
the LLC capacity, thus degrading performance due to high
memory bandwidth pressure. Recent work has reduced the
I/O working set size by sharing Rx rings among cores with the
"shRing" system. But this approach suffers from a bottleneck
under imbalanced loads, which are common.

We contend that the bottleneck stems from an unnecessary entanglement of two
orthogonal producer-consumer structures: (1) memory allocation, where the core
produces empty buffers that the NIC consumes to store packets; and (2) packet
delivery, where the NIC produces incoming packets that the core consumes. We
propose rxBisect, a new CPU-NIC interface that decouples these structures.
RxBisect replaces each Rx ring with two separate rings corresponding to the two
structures, allowing memory allocation to be performed independently of packet
reception. RxBisect can thus pass empty buffers efficiently between cores upon
imbalance, thereby eliminating the aforementioned bottleneck. We implement
rxBisect with software emulation and find that it improves throughput by up to
20% and 37% relative to the state-of-the art (shRing) and state-of-the-practice
(per-core Rx rings).
