---
title: "Using 'git send-email' with GMail (TLS) on macOS via brew"
date: 2017-07-26 20:18:32 -0200
layout: post
categories: personal learning
---
I spent some time searching the web for a way to configure and use `git send-email` using `brew`, so the impact on the provided system Perl and other tools were minimized (avoiding sudo completely). But I got disappointed with my findings...<!--more-->

They instruct you to use brew's git, but give instructions to install the required perl extensions for TLS SMTP communications into the system Perl, using `sudo` to do so. This definitely wasn't what I was looking for.

I spent some time looking for a way to constrain the required changes to remain inside `brew` domain, and after some time, I figure it out.
This is what you need to do, with its why's.

The macOS system provided git, as well as the brew's pre compiled one, provide support only for system Perl, so if you need git to use your brew's Perl CPAN modules, you have to "brew custom build" it, with some additional parameters.

If you have brew's git already installed, you need to remove it with the following command.

`brew remove git`

Then install brew git again with options to make it dependent on brew's Perl

`brew install git --with-openssl --with-perl --with-subversion`

This will build git with the provided parameters, adding support for brew's Perl with all it's CPAN modules (as well as the ones that you will install manually). Notice that as this build is dependent on Perl, it *will* install brew's Perl, if not yet installed (as well as brew's OpenSSL and Subversion).

The next step would be to instal the cpan minus tool, that helps resolve CPAN module dependencies automatically, laying out the remaining CPAN module installations a lot smoother.

`brew install cpanminus`

That's all that you need to have a brew's git version that uses brew's Perl, OpenSSL and Subversion (for svn integration). Now, all that you have to do, is complete the installation of the required CPAN modules for GMail SMTP TLS connections support.

The commands to do so are:

`cpanm Net::SMTP::SSL`

`cpanm Authen::SASL`

After all of this, you should be able to run a `git format-patch` and then send it with `git send-email` using a GMail account and its default SMTP TLS connection.

I strongly recommend you to setup your gmail account for 2-factor authentication and then create an application specific password for git send-email. This will greatly reduce the risk of compromising your GMail account. If you are unsure about how to achieve this, search google for "how to set an application specific password in gmail", or you can take a look at this good tutorial [].

I hope that this have helped you setting git without tampering too much with the installed macOS system.
