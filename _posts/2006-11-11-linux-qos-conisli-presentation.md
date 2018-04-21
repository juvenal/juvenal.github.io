---
layout: post
date: 2006-11-11 10:18:02 -0200
title: Linux QoS CONISLI presentation
subtitle:
use_math: true
categories: personal learning
abstract: |
  CONISLI is an acronym for (in portuguese) "CONgresso Internacional de Software LIvre", or in english "Free Software International Conference". I was one of the presenters this year, and my presentation title was (in portuguese) _"QoS e Serviços Diferenciados usando Linux"_, or in english _"QoS and Differentiated Services using Linux"_.
---
I was one of the presenters in this year's CONISLI event at the "Anhembi's Conference Bow" in São Paulo.<!--more--> I chose this topic mainly because I had spent a lot of time working with the Linux kernel network stack, as well as implementing some network link optimizations for some of my clients. In most of them, we were able to better use the currently contracted bandwidth with room to spare.


I stumbled at the Linux kernel network stack when I had to integrate the Cyclades PC-300 drivers into kernel 2.4 (the original drivers were written for kernel 2.2). The PC-300 is a syncronous serial interface (with V.35 support), commonly used to connect digital link "modems" provided by the public telco network. Using this PCI card, I connected some of my customers networks with the Internet using the HDLC protocol. The kernel upgrade from 2.2 to 2.4 broke the drivers HDLC protocol implementation, as kernel 2.4 began to provide better native support for it. I spent a week integrating the drivers HDLC into the new HDLC kernel code, and sent my changes back to Cyclades, for inclusion in the next release of the driver. That experience gave me some deep insights on the kernel network stack.


My presentation covers much of my link optimization techniques applied afterwards this, but it delves briefely into the Linux kernel network stack details that make all the QoS stuff work.


I made my presentation available in [Slideshare](http://slidesha.re/cq66S7), and I hope that it was of good use to you, as I hope it was for the conference's listeners.