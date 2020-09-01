---
title: "Storm: a fast transactional dataplane for remote data structures"
collection: publications
permalink: /publications/2019-storm
excerpt: ''
date: 2019-6-4
venue: "SYSTOR '19, Proceedings of the 12th ACM International Conference on Systems and Storage"
paperurl: '/files/2019-storm.pdf'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Stanko Novakovic, Yizhou Shan, Aasheesh Kolli, Michael Cui, Yiying Zhang, Haggai Eran, Boris Pismenny, Liran Liss, Michael Wei, Dan Tsafrir, Marcos Aguilera 
notes: Awarded best paper.
best: 1
#abstract: 1
---

RDMA is an exciting technology that enables a host to access the memory of a
remote host without involving the remote CPU. Prior work shows how to use RDMA
to improve the performance of distributed in-memory storage systems. However,
RDMA is widely believed to have scalability issues, due to the amount of active
protocol state that needs to be cached in the limited NIC cache. These concerns
led to several software-based proposals to enhance scalability by trading off
performance. In this work, we revisit these trade-offs in light of newer RDMA
hardware and propose new guidelines for scaling RDMA. We show that using
one-sided remote memory primitives leads to higher performance compared to
send/receive and kernel-based systems in rack-scale environments. Based on
these insights, we design and implement Storm, a transactional dataplane using
one-sided read and write-based RPC primitives. We show that Storm outperforms
eRPC, FaRM, and LITE by 3.3x, 3.6x, and 17.1x, respectively, on an Infinband
EDR cluster with Mellanox ConnectX-4 NICs.
