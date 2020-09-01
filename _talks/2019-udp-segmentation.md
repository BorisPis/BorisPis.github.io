---
title: "UDP segmentation offload"
collection: talks
permalink: /talks/2018-udp-segmentation-offload
excerpt: ''
date: 2018-07-13
venue: "netdev 0x12, Proceedings of NetDev 0x12: The Technical Conference on Linux Networking"
paperurl: 'https://netdevconf.info/0x12/session.html?udp-segmentation-offload'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Yossi Kupperman
---

UDP segmentation was recently introduced to the Linux kernel. Even though this
is a new netdev features, some existing devices (e.g. ixgbe, ConnectX-4, and
ConnectX-5) may be able to support it.

In this talk, we will present our efforts towards supporting UDP segmentation
offload with existing devices.  The limitations we have encountered. How we
overcome these limitations. Finally, we suggest potential improvements to the
Linux networking stack to generalize our work and make driver development
easier.
