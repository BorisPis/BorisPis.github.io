---
title: "TLS Offload to Network Devices"
collection: publications
permalink: /publications/2016-tls-offload
excerpt: ''
date: 2016-10-05
venue: "netdev 1.2, Proceedings of NetDev 1.2: The Technical Conference on Linux Networking"
paperurl: 'https://netdevconf.org/1.2/papers/netdevconf-TLS.pdf'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Ilya Lesokhin, Liran Liss, Haggai Eran
---

Encrypted Internet traffic is becoming the norm, spearheaded by
the use Transport Layer Socket (TLS) to secure TCP connections.
This trend introduces a great challenge to data center servers, as
the symmetric encryption and authentication of TLS records adds
significant CPU overhead. New CPU capabilities, such as the x86
AES-NI instruction set, alleviate the problem, yet encryption
overhead remains high. Alternatively, cryptographic accelerators
require dedicated HW, consume significant memory bandwidth,
and increase latency. We propose to offload TLS symmetric
crypto processing to the network device. Our solution does not require
a TCP Offload Engine (TOE). Rather, crypto processing is
moved to a kernel TLS module (kTLS), which may leverage
inline TLS acceleration offered by network devices. Transmitted
packets of offloaded TLS connections pass through the stack unencrypted,
and are processed on the fly by the device. Similarly,
received packets are decrypted by the device before being handed
off to the stack. We will describe the roles and requirements of
the kTLS module, specify the device offload APIs, and detail the
TLS processing flows. Finally, we will demonstrate the potential
performance benefits of network device TLS offloads.
