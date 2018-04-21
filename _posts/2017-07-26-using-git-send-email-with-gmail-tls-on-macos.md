---
layout: post
date: 2017-07-26 20:18:32 -0200
title: "Configure 'git send-email' with GMail (TLS)"
subtitle: "How to set it up without tamper with the macOS system (no sudo)"
comments: true
categories: personal learning
abstract: |
  The usage of `git format-patch` and `git send-mail` is highly common between open source developers that use mailing lists to review and comment patches (notably the GNU C library). I will not cover the steps to prepare and send a patch using these git commands in this post, as they are straightforward to accomplish, reading their man pages. I will show here a way to configure them in the least possible impact to the (macOS) system files and utilities (no `sudo` used).
---
<!--more-->

### On this post
{: .no_toc}

* Will be replaced by the TOC generated content
{:toc .toc-class}

### Problem

Working on Open Source projects is fun, but you have to do your homework to contribute. Most GNU communities rely on patch review and approval by mailing lists. You can wrap your patch and compose an email with it manually, avoiding the fancy text formatting that most email clients provide by default today, but it's really a lot easier to use `git format-patch` and `git send-mail` to have it done. Using them gives greater confidence that it will meet the requirements of the mailing list patch format...

Having that said, I think that the clear choice will be to have these tools properly configured for use. I avoid, as much as possible, to install or modify system files and libraries. To do so, and keep the UNIX command line utilities up-to-date as much as possible in my macOS machine, without interfering with the system packages, I use [homebrew](https://brew.sh), and update it as frequently as possible (using `brew update && brew upgrade && brew cleanup` on a regular basis).

I want to configure `git format-patch` and `git send-mail` to use my GMail account to send the patches that I had to contribute, mainly because it is well known to some people on these lists. The main problem with this is that GMail SMTP servers require TLS secure connections, and as `git send-mail` uses Perl to perform the network connections, it needs extra CPAN packages to work cleanly with TLS encryption.

I googled the internet for a way to install and configure the required Perl CPAN modules to enable TLS connections, but all the answer/tutorial pages that I found instructed the user to add CPAN modules to the system Perl.

I don't want to mess with macOS system files, or change/add dependencies to them, so those solutions weren't viable to me. I started to think about setting everything inside homebrew, so it would be isolated form system Perl and other macOS system files. Eventually I figured out a really simple way to configure all required tools without tamper with the macOS system entirely...

### Solution

The easiest way to meet my requirements and configure `git send-mail` to work with GMail TLS servers, is to install the homebrew version of git with some additional parameters, so that the install won't try to use the precompiled package, which links against macOS system Perl, and as consequence, requires the install of the additional Perl CPAN modules at system places (and thus, the need for sudo to do so). When you pass some parameters to `brew install <package-name>` it assumes that you want to build a custom version of the given package. There is a git install parameter on brew that instructs the build to link against brew Perl, and it's enough to keep it off of system Perl. 😀

If you just install git directly from brew, you got it precompiled for your version of macOS. If you already have it installed via brew, the following command returns the currently installed version

```
$ brew info git
git: stable 2.15.0 (bottled), HEAD
Distributed revision control system
https://git-scm.com
/usr/local/Cellar/git/2.15.0 (1,497 files, 37.2MB) *
  Poured from bottle on 2018-03-05 at 09:37:31
From: https://github.com/Homebrew/homebrew-core/blob/master/Formula/git.rb
...
```

Note the 'Poured' line. It indicates that the git version that you have installed is a precompiled one. By default, brew formulas rely on system libraries and utilities most of the time to build its tools, It is a way to reduce dependencies on its own (brew) packages.




```
  Built from source on 2018-04-10 at 08:31:51 with: --with-subversion --with-openssl
```


### Conclusion

This method has several advantages over the others that mess with macOS system files. The first one is that a macOS security update may unexpectedly break your config and/or settings...
Another problem is clear when you upgrade your machine... The macOS system is well known for its easy of use

### Updates

#### 2018-03-19



I spent some time searching the web for a way to configure and use `git send-email` using `brew`, so the impact on the provided system Perl and other tools were minimized (avoiding sudo completely). But I got disappointed with my findings.<!--more-->


They instruct you to use brew's git, but give instructions to install the required perl extensions for TLS SMTP communications into the system Perl, using `sudo` to do so. This definitely wasn't what I was looking for.


I spent some time looking for a way to constrain the required changes to remain inside `brew` domain, and after some time, I figure it out.
This is what you need to do, with its why's.


The macOS system provided git, as well as the brew's pre compiled one, provide support only for system Perl, so if you need git to use your brew's Perl CPAN modules, you have to "brew custom build" it, with some additional parameters.


If you have brew's git already installed, you need to remove it with the following command.

`brew remove git`


Then install brew git again with options to make it dependent on brew's Perl

`brew install git --with-openssl --with-perl --with-subversion`


This will build git with the provided parameters, adding support for brew's Perl with all it's CPAN modules (as well as the ones that you will install manually). Notice that as this build is dependent on Perl, it _will_ install brew's Perl, if not yet installed (as well as brew's OpenSSL and Subversion).


The next step would be to instal the cpan minus tool, that helps resolve CPAN module dependencies automatically, laying out the remaining CPAN module installations a lot smoother.

`brew install cpanminus`


That's all that you need to have a brew's git version that uses brew's Perl, OpenSSL and Subversion (for svn integration). Now, all that you have to do, is complete the installation of the required CPAN modules for GMail SMTP TLS connections support.


The commands to do so are:

`cpanm Net::SMTP::SSL`

`cpanm Authen::SASL`


After all of this, you should be able to run a `git format-patch` and then send it with `git send-email`
 using a GMail account and its default SMTP TLS connection.

**UPDATE 2018-03-19**

If after some time, and brew updates to git and perl, you start to get this error on `git send-email`:
```
Not using SSL_VERIFY_PEER due to out-of-date IO::Socket::SSL.
To use SSL please install IO::Socket::SSL with version>=2.007 at <brew_install_path_of_cpan_module>
```
just repeat the cpanm commands above. It should update the outdated components and everything gets back to normal.


I strongly recommend you to setup your gmail account for 2-factor authentication and then create an application specific password for git send-email. This will greatly reduce the risk of compromising your GMail account. If you are unsure about how to achieve this, search google for "how to set an application specific password in gmail", or you can take a look at [this good tutorial](https://www.lifewire.com/get-a-password-to-access-gmail-by-pop-imap-2-1171882), or [this one](https://www.shoutmeloud.com/how-to-generate-google-app-specific-password-2-step-verification.html).


I hope that this have helped you setting git without tampering too much with the installed macOS system.
