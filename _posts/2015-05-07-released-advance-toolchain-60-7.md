---
layout: post
date: 2015-05-07 16:08:24 -0200
title: Released Advance Toolchain 6.0-7
subtitle: 
categories: work ibm-ltc
---
A new update release for the 6.0 series of the IBM Advance Toolchain for Linux on POWER is now available.<!--more-->

This is a maintenance release for the 6.0 series (6.0-7) and contains a series of fixes. Among them, it provides:

- OpenSSL fixes for security advisories:
  - Segmentation fault in ASN1_TYPE_cmp fix ([CVE-2015-0286](https://www.openssl.org/news/vulnerabilities.html#2015-0286))
  - ASN.1 structure reuse memory corruption fix ([CVE-2015-0287](https://www.openssl.org/news/vulnerabilities.html#2015-0287))
  - PKCS7 NULL pointer dereferences fix ([CVE-2015-0289](https://www.openssl.org/news/vulnerabilities.html#2015-0289))
  - DoS via reachable assert in SSLv2 servers fix ([CVE-2015-0293](https://www.openssl.org/news/vulnerabilities.html#2015-0293))
  - Use After Free following d2i_ECPrivatekey error fix ([CVE-2015-0209](https://www.openssl.org/news/vulnerabilities.html#2015-0209))
  - X509_to_X509_REQ NULL pointer deref fix ([CVE-2015-0288](https://www.openssl.org/news/vulnerabilities.html#2015-0288))
  - Removed the export ciphers from the DEFAULT ciphers
  - Fix for [CVE-2014-3571](https://www.openssl.org/news/vulnerabilities.html#2014-3571)
  - Fix for [CVE-2015-0206](https://www.openssl.org/news/vulnerabilities.html#2015-0206)
  - Fix for [CVE-2014-3569](https://www.openssl.org/news/vulnerabilities.html#2014-3569)
  - Fix for [CVE-2014-3572](https://www.openssl.org/news/vulnerabilities.html#2014-3572)
  - Fix for [CVE-2015-0204](https://www.openssl.org/news/vulnerabilities.html#2015-0204)
  - Fix for [CVE-2015-0205](https://www.openssl.org/news/vulnerabilities.html#2015-0205)
  - Fix for [CVE-2014-8275](https://www.openssl.org/news/vulnerabilities.html#2014-8275)
  - Fix for [CVE-2014-3570](https://www.openssl.org/news/vulnerabilities.html#2014-3570)
- The GNU C Library fixes for security advisories:
  - [CVE-2013-1914](https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2013-1914)
  - [CVE-2013-7423](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2013-7423)
  - [CVE-2015-1472](https://sourceware.org/bugzilla/show_bug.cgi?id=16618) and [CVE-2015-1473](https://sourceware.org/bugzilla/show_bug.cgi?id=16618)
  - [CVE-2015-0235](https://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2015-0235)
  - [CVE-2014-9402](http://web.nvd.nist.gov/view/vuln/detail?vulnId=CVE-2014-9402)
- Binutils fixes for security advisories:
  - [CVE-2014-8738](https://sourceware.org/bugzilla/show_bug.cgi?id=17533)

For download links, more information and documentation, please refer to our [official documentation page](http://ibm.co/AdvanceToolchain). Please, [let us know](https://www.ibm.com/developerworks/community/groups/service/html/communityview?communityUuid=fe313521-2e95-46f2-817d-44a4f27eba32#fullpageWidgetId%3DW72c1fc20d34a_4a14_8dec_82de60002bab&forumsPg=null&topicsPg=null) if you have any questions about this release.

#### About the IBM Advance Toolchain for Linux on Power

The IBM Advance Toolchain for PowerLinux is a set of open source development tools (compiler, debugger and profiling tools) and runtime libraries that allow users to take leading edge advantage of IBM's latest POWER hardware features on Linux.

For more information about it, visit [our page](http://ibm.co/AdvanceToolchain).
