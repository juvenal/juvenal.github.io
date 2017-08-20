---
title: Released Advance Toolchain 9.0-1
date: 2015-12-09 17:01:23 -0200
layout: post
categories: work ibm-ltc
---
A new update release for the 9.0 series of the IBM Advance Toolchain for Linux on Power is now available.

This is a maintenance release for the 9.0 series (9.0-1) and contains a series of fixes:

- Expat provides a fix for CVE-2015-1283.
- Support for Fedora 22 ppc64le.
- GCC fix for HTM builtins aren't treated as compiler barriers on PowerPC.
- The GNU C Library provides:
  - Fix for memory corruption when using getmntent on blank lines.
  - Always enable pointer guard.
- libdfp fix for fabs() is returning wrong values for 128-bit.

Also, a tool to download AT is now available at  ftp://ftp.unicamp.br/pub/linuxpatch/toolchain/at/at_downloader/

For download links, more information and documentation, please refer to our official documentation page.

Please let us know if you have any questions about this release.

#### About the IBM Advance Toolchain for PowerLinux

The IBM Advance Toolchain for PowerLinux is a set of open source development tools (compiler, debugger and profiling tools) and runtime libraries that allow users to take leading edge advantage of IBM's latest POWER hardware features on Linux.
For more information about it, visit http://ibm.co/AdvanceToolchain.
