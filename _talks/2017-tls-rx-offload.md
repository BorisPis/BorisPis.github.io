---
title: "TLS Receive Side Crypto Offload"
collection: talks
permalink: /talks/2017-tls-rx-offload
type: "Talk"
excerpt: ''
date: 2017-11-08
venue: "netdev 2.2, Proceedings of NetDev 2.2: The Technical Conference on Linux Networking"
location: "Seoul, Korea"
extlink: 'https://netdevconf.info/2.2/session.html?pismenny-tlscrypto-talk'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Boris Pismenny, Ilya Lesokhin, Liran Liss
---

In this talk we present the challenges of TLS receive side crypto offload, such
as reordering and packet loss. Our goal is to assist the kernel with offloading
the compute-intensive cypto tasks while leaving TCP processing unmodified. We
present a design and implementation of a solution that addresses these
problems. We evaluate the performance of TLS offload from several aspects.
