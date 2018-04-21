---
layout: post
title: "Began project 'github-cli'"
subtitle: "An utility for basic Github interaction right from the command line"
date: 2017-08-16 12:14:21 -0200
use_math: true
use_mermaid: true
categories: personal projects
abstract: |
  Github is *really nice*, don't get me wrong, but for people that rely mostly on the command line, having to go to an additional application or, most likely, the web browser to interact with it, may be a pain. I am having this feeling multiple times a day lately, so I began this little project to have an easy way to access Github's most common features from the command line directly.
---

One thing that always bothered me with GitHub when using the terminal was the lack of a CLI utility to interact with it. You always have to open a browser, head to the GitHub page and perform the action that you need to.<!--more-->
On macOS, Xcode 9 does some tricks and integrate the IDE with Github to a certain level. I'd like to have something similar, but at the command line. This also looked like a perfect opportunity to sharp my skills on the Go language, or at least get the rust off of it.

The `github-cli` utility was designed following the pattern below:
```
github-cli <verb> <options>...
```
I implemented three verbs, that cover most of my basic needs. They are `login`, `repo` and `org`. Their related options are tight to the verb's original function, as well as its parameters.

This project also makes github usefull for automation scripts. It makes possible to use a lot of information that would not be easily available by other means to an automation script. The main idea of the project is to provide things like `github-cli repo` to get a list of repositories for the logged user. Or `github-cli org` to retrieve the current logged user's organizations. Those verbs ('repos' and 'orgs') have options to filter the possible results

I'm planning to add some more options for different filters of the returned values. Other verbs are under review too, like adding something as `github-cli issues` to get opened issues, althought it's not the priority right now. I am really open to new ideas and possibilities, so I'd like to hear your comments to know what else would be helpful to you, heavy CLI users, to add to this tool.

The project is available at [Github](https://github.com/juvenal/github-cli)

That's the main reason behind this small project. To provide a command line tool that directly interacts with the GitHub REST API to provide some services directly on the command line.
