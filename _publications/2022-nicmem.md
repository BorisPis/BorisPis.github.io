---
title: "The Benefits of General-Purpose On-NIC Memory"
collection: publications
permalink: /publications/2022-nicmem
excerpt: ''
date: 2022-02-28
prevenue: "ASPLOS '22: ACM International Conference on Architectural Support for Languages and Operating Systems"
paperurl: '/files/2022-nicmem.pdf'
slides: '/files/2022-nicmem-slides.pdf'
poster: '/files/2022-nicmem-poster.pdf'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Liran Liss, Adam Morrison, Dan Tsafrir
#best: 1
#distinguished: 1
#abstract: 1
---
We propose to use the small, newly available on-NIC memory
("nicmem") to keep pace with the rapidly increasing performance of
NICs. We motivate our proposal by accelerating two types of workload
classes: NFV and key-value stores.
As NFV workloads frequently operate on headers---rather than data---of
incoming packets, we introduce a new packet-processing architecture
that splits between the two, keeping the data on nicmem when possible
and thus reducing PCIe traffic, memory bandwidth, and CPU processing
time. Our approach consequently shortens NFV latency by up to
23% and increases its throughput by up to 19%.
Similarly, because key-value stores commonly exhibit skewed
distributions, we introduce a new network stack mechanism that lets
applications keep frequently accessed items on nicmem. Our design
shortens memcached latency by up to 43% and increases its
throughput by up to 80%.
