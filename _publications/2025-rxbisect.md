---
title: "Disentangling the dual role of NIC receive rings"
collection: publications
permalink: /publications/2025-rxbisect
excerpt: ''
date: 2025-07-07
prevenue: "OSDI '25: USENIX Symposium on Operating Systems Design and Implementation"
#paperurl: '/files/2025-rxbisect.pdf'
#defpaperurl: https://www.usenix.org/conference/osdi25/presentation/pismenny
#slides: '/files/2025-rxbisect-slides.pptx'
#poster: '/files/2025-rxbisect-poster.pdf'
#video: 'https://youtu.be/qot-gTh37MU'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Adam Morrison, Dan Tsafrir
#best: 1
#distinguished: 1
#abstract: 1
---
CPUs parallelize packet processing on multiple cores via per-core
receive ("Rx") rings that are sized to absorb bursts (≥1Ki entries
by default). The resulting I/O working set---all packet buffers pointed to by
all Rx rings---easily exceeds the LLC capacity, resulting in decreased
performance due to high memory bandwidth.
Recent work has minimized the I/O working set size by sharing Rx buffers among
cores via the existing Rx ring interface. However, this approach encounters a
bottleneck during imbalanced loads, a situation that is not uncommon.

We contend that this bottleneck is caused by the unnecessarily entangled nature
of two orthogonal "producer-consumer" functionalities: (1) memory allocation,
whereby the core "produces" empty buffers that the NIC "consumes" for storing
packets; and (2) packet delivery, whereby the NIC "produces" incoming packets
that the core "consumes" (receives).

We propose rxBisect, a new CPU-NIC interface, which decouples these functionalities. RxBisect
substitutes each Rx ring with two rings that correspond to
the two functionalities, such that memory allocation is done
independently of packet reception. RxBisect can thus
efficiently pass empty buffers between cores in all scenarios.
We implement RxBisect using software emulation.
RxBisect improves throughput by up to 20% and reduces latency by up to
11x. The significant latency gains occur when rxBisect meets
line rate load whereas the baseline fails to do so.
