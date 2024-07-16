---
title: "NIC-software interfaces"
collection: talks
permalink: /talks/2024-dagstuhl
type: "Talk"
excerpt: ''
date: 2024-07-16
venue: "Dagstuhl"
location: "Dagstuhl, Germany"
#extlink: ''
slides: '/files/2024-dagstuhl-nic-software-interfaces.pptx'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny
---
Network software interface are evolving with technology trends. We show several
technology trends in server CPUs and NICs. We show data suggesting that NIC
upgrades are more cost-effective relative to CPU upgrades. We also show that
NIC offloads are mostly free. These together motivate us to look at offloading
CPU functionality to the NIC. We then show a two trends about CPUs available
from Intel, AMD, and ARM vendors: (1) CPU I/O speeds are growing faster than
CPU core number; and (2) CPU I/O speeds are growing faster than CPU memory
bandwidth.  These indicate that cores are increasingly unable to process data
at line-rate and that memory bandwidth isn't sufficient to store all I/O data,
making NIC offloads and other ways the NIC can improve CPU efficiency even more
important.

We discuss several software techniques to optimize performance: batching at
different layers of the I/O stack; zerocopy on receive, transmit, within
applications, and by using device memory. We discuss research that tackles
memory bandwidth bottlenecks by backpressure on cores and the network, and
research that fits the workload to the last-level cache to benefit from DDIO.

We also discuss several NIC hardware techniques to deal with multi-core CPUs
that introduce challenges on fair and efficient packet scheduling on transmit
and receive. The I/O working set problem on receive. And also advances in NIC
SRIOV support that enable matching paravirtualized NIC functionality while
gaining the performance benefits of SRIOV. Last, we present works for specific
applications: network functions, and transport and application offloads. 
