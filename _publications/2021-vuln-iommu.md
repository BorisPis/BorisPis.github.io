---
title: "Characterizing, Exploiting, and Detecting DMA Code Injection Vulnerabilities in the Presence of an IOMMU"
collection: publications
permalink: /publications/2021-iommu-vuln
excerpt: ''
date: 2021-04-26
venue: "EuroSys '21: European Conference on Computer Systems"
#paperurl: '/files/2021-iommu-vuln.pdf'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Alex Markuze, Shay Vargaftik, Gil Kupfer, Boris Pismenny, Nadav Amit, Adam Morrison, and Dan Tsafrir
#best: 1
#abstract: 1
---
Direct Memory Access (DMA) makes the system vulnerable
to DMA attacks, in which I/O devices access memory
regions not intended for their use. Hardware IOMMU protection
cannot prevent all DMA attacks because it restricts
DMA at page-level granularity leading to sub-page vulnerabilities.
Conventional wisdom is that sub-page vulnerabilities
that lead to viable DMA attacks are made possible by buggy
device drivers or poor (but isolated) driver design choices.

This paper disproves the above belief, showing that it is
often the kernel design that enables a DMA attack. To this
end, we first categorize sub-page vulnerabilities into four
categories, providing insight into the structure of DMA
vulnerabilities. Then, to exploit these vulnerabilities, we
identify a set of three vulnerability attributes which are
sufficient to execute code injection attacks.

We then build analysis tools that detect sub-page
vulnerabilities and analyze the Linux kernel. We find that 72%
of the device drivers expose sensitive callback pointers, which
may be overwritten by a device to hijack kernel control flow.

Aided by the tools’ output, we demonstrate novel code
injection attacks on the Linux kernel we term compound
attacks. Specifically, while all previously reported attacks are
single-step, i.e., with the vulnerability attributes present in a
single page, in compound attacks, the vulnerability attributes
are initially incomplete. However, they can be attained by
carefully exploiting standard OS behavior.
