---
title: "Rowhammering Storage Devices"
collection: publications
permalink: /publications/2021-ssd-rowhammer
excerpt: ''
date: 2021-07-30
venue: "HotStorage '21: ACM Workshop on Hot Topics In Storage and File Systems"
paperurl: '/files/2021-ssdhammer.pdf'
video: 'https://youtu.be/-fJo5fDH0Ik?t=5696'
defpaperurl: 'https://dl.acm.org/doi/10.1145/3465332.3470871'
#citation: 'Your Name, You. (2009). &quot;Paper Title Number 1.&quot; <i>Journal 1</i>. 1(1).'
authors: Tao Zhang, Boris Pismenny, Donald E. Porter, Dan Tsafrir, and Aviad Zuck
#best: 1
#abstract: 1
---
Peripheral devices like SSDs are growing more complex, to the point
they are effectively small computers themselves. Our position is that
this trend creates a new kind of attack vector, where untrusted
software could use peripherals strictly as intended to accomplish
unintended goals. To exemplify, we set out to rowhammer the DRAM
component of a simplified SSD firmware, issuing regular I/O requests
that manage to flip bits in a way that triggers sensitive information
leakage. We conclude that such attacks might soon be feasible, and we
argue that systems need principled approaches for securing peripherals
against them.
