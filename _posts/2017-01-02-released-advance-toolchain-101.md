---
title: "Released Advance Toolchain 10.0-1"
date: 2017-01-02 17:06:43 -0200
layout: post
categories: work ibm-ltc
---
A new update release for the 10.0 series of the IBM Advance Toolchain for Linux on Power is now available.<!--more-->

This release provides new features and many package updates, including:

- POWER9 tuned libraries.
- The GNU C Library provides:
  - POWER9 implies fixed.
  - Fixes powerpc [ifunc-sel.h with GCC 6](https://sourceware.org/ml/libc-alpha/2016-07/msg00574.html) and [ifunc-sel.h asm constraints and clobber list](https://sourceware.org/ml/libc-alpha/2016-07/msg00588.html).
  - Fix for [argp.h overwriting GCC keywords with macros](https://sourceware.org/bugzilla/show_bug.cgi?id=16907).
  - Fix for [objects in libc.a being overwritten in other static libraries](https://sourceware.org/bugzilla/show_bug.cgi?id=20452).
- Binutils provides:
  - POWER9 support matching final ISA 3.0.
  - Fix for PowerPC64 ELFv1 undefined weak functions.
  - Fix [PowerPC64 ifunc confusion](https://sourceware.org/bugzilla/show_bug.cgi?id=20472).
  - Fix for [powerpc apuinfo for spe parsed incorrectly](https://sourceware.org/bugzilla/show_bug.cgi?id=20531).
  - New gold option: -z stack-size.
- Boost provides 128 bytes of cache line for lockfree data structures.
- OpenSSL provides fixes for [CVE-2016-6309 and CVE-2016-7052](https://www.openssl.org/news/secadv/20160926.txt).
- Python fixes [CVE-2016-5636: heap overflow in zipimporter module](https://bugs.python.org/issue26171).

For download links, more information and documentation, please refer to our [official documentation page](http://ibm.co/AdvanceToolchain). Please, [let us know](https://www.ibm.com/developerworks/community/groups/service/html/communityview?communityUuid=fe313521-2e95-46f2-817d-44a4f27eba32#fullpageWidgetId%3DW72c1fc20d34a_4a14_8dec_82de60002bab&forumsPg=null&topicsPg=null) if you have any questions about this release.

#### About the IBM Advance Toolchain for Linux on Power

The IBM Advance Toolchain for Linux on Power is a set of open source development tools (compiler, debugger and profiling tools) and runtime libraries that allow users to take leading edge advantage of IBM's latest POWER hardware features on Linux.
For more information about it, visit [our page](http://ibm.co/AdvanceToolchain).