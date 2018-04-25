---
title: Released Advance Toolchain 10.0-0
date: 2016-09-13 16:22:36 -0200
layout: post
categories: work ibm-ltc
---
We released a major version of the IBM Advance Toolchain for Linux on POWER is now available.<!--more-->

- Advance Toolchain 10.0-0

  The new features available are listed below:

  - Support for Ubuntu 16.04.
  - GCC provides fixes for complex IEEE 128-bit floating point and support for IEEE 128-bit floating point built-ins.
  - GCC creates binaries using --mcpu=power8 --mtune=power8 by default on ppc64le.
  - Valgrind provides a fix for [missing support for wbit field on mtfsfi instruction](https://bugs.kde.org/show_bug.cgi?id=362894).
  - Valgrind Itrace provides a new option to only start instruction tracing when a given function starts.
  - Cross-compiler packages are now signed.
  - OpenSSL provides [6 security advisories](https://www.openssl.org/news/secadv/20160503.txt).

For download links, more information and documentation, please refer to our [official documentation page](http://ibm.co/AdvanceToolchain). Please, [let us know](https://www.ibm.com/developerworks/community/groups/service/html/communityview?communityUuid=fe313521-2e95-46f2-817d-44a4f27eba32#fullpageWidgetId%3DW72c1fc20d34a_4a14_8dec_82de60002bab&forumsPg=null&topicsPg=null) if you have any questions about this release.

#### About the IBM Advance Toolchain for PowerLinux

The IBM Advance Toolchain for PowerLinux is a set of open source development tools (compiler, debugger and profiling tools) and runtime libraries that allow users to take leading edge advantage of IBM's latest POWER hardware features on Linux.
For more information about it, visit [our page](http://ibm.co/AdvanceToolchain).