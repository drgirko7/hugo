---
title: Git
subtitle: Software for tracking changes

# Summary for listings and search engines
summary: Git is a software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development.

# Link this post with a project
projects: []

# Date published
date: '2020-12-13T00:00:00Z'

# Date updated
lastmod: '2020-12-13T00:00:00Z'

# Is this an unpublished draft?
draft: false

# Show this page in the Featured widget?
featured: false

# Featured image
# Place an image named `featured.jpg/png` in this page's folder and customize its options here.
image:
  caption: '[**git**]()'
  focal_point: ''
  placement: 2
  preview_only: false

authors:
  - admin

tags:
  - Academic

categories:
  - Demo
---

## Overview

Git is a software for tracking changes in any set of files, usually used for coordinating work among programmers collaboratively developing source code during software development. Its goals include speed, data integrity, and support for distributed, non-linear workflows (thousands of parallel branches running on different systems).

Git was originally authored by Linus Torvalds in 2005 for development of the Linux kernel, with other kernel developers contributing to its initial development. Since 2005, Junio Hamano has been the core maintainer. As with most other distributed version control systems, and unlike most client–server systems, every Git directory on every computer is a full-fledged repository with complete history and full version-tracking abilities, independent of network access or a central server.Git is free and open-source software distributed under the GPL-2.0-only license.

## History
Git development began in April 2005, after many developers of the Linux kernel gave up access to BitKeeper, a proprietary source-control management (SCM) system that they had been using to maintain the project since 2002. The copyright holder of BitKeeper, Larry McVoy, had withdrawn free use of the product after claiming that Andrew Tridgell had created SourcePuller by reverse engineering the BitKeeper protocols. The same incident also spurred the creation of another version-control system, Mercurial.

Linus Torvalds wanted a distributed system that he could use like BitKeeper, but none of the available free systems met his needs. Torvalds cited an example of a source-control management system needing 30 seconds to apply a patch and update all associated metadata, and noted that this would not scale to the needs of Linux kernel development, where synchronizing with fellow maintainers could require 250 such actions at once. For his design criterion, he specified that patching should take no more than three seconds, and added three more goals:

* Take Concurrent Versions System (CVS) as an example of what _not_ to do; if in doubt, make the exact opposite decision.
* Support a distributed, BitKeeper-like workflow.
* Include very strong safeguards against corruption, either accidental or malicious.

These criteria eliminated every version-control system in use at the time, so immediately after the 2.6.12-rc2 Linux kernel development release, Torvalds set out to write his own.

The development of Git began on 3 April 2005. Torvalds announced the project on 6 April and became self-hosting the next day. The first merge of multiple branches took place on 18 April. Torvalds achieved his performance goals; on 29 April, the nascent Git was benchmarked recording patches to the Linux kernel tree at the rate of 6.7 patches per second. On 16 June, Git managed the kernel 2.6.12 release.

Torvalds turned over maintenance on 26 July 2005 to Junio Hamano, a major contributor to the project. Hamano was responsible for the 1.0 release on 21 December 2005 and remains the project’s core maintainer.

## Naming
Torvalds sarcastically quipped about the name _git_ (which means “unpleasant person” in British English slang): “I’m an egotistical bastard, and I name all my projects after myself. First ‘Linux’, now ‘git’.” The man page describes Git as “the stupid content tracker”. The read-me file of the source code elaborates further:

* “git” can mean anything, depending on your mood.
    
* Random three-letter combination that is pronounceable, and not actually used by any common UNIX command. The fact that it is a mispronunciation of “get” may or may not be relevant.
    
* Stupid. Contemptible and despicable. Simple. Take your pick from the dictionary of slang.
    
* “Global information tracker”: you’re in a good mood, and it actually works for you. Angels sing, and a light suddenly fills the room.
    
* “Goddamn idiotic truckload of sh*t”: when it breaks.

## Implementations
Git (the main implementation in C) is primarily developed on Linux, although it also supports most major operating systems, including the BSDs (DragonFly BSD, FreeBSD, NetBSD, and OpenBSD), Solaris, macOS, and Windows.

The first Windows port of Git was primarily a Linux-emulation framework that hosts the Linux version. Installing Git under Windows creates a similarly named Program Files directory containing the Mingw-w64 port of the GNU Compiler Collection, Perl 5, MSYS2 (itself a fork of Cygwin, a Unix-like emulation environment for Windows) and various other Windows ports or emulations of Linux utilities and libraries. Currently, native Windows builds of Git are distributed as 32- and 64-bit installers. The git official website currently maintains a build of Git for Windows, still using the MSYS2 environment.

The JGit implementation of Git is a pure Java software library, designed to be embedded in any Java application. JGit is used in the Gerrit code-review tool, and in EGit, a Git client for the Eclipse IDE.

Go-git is an open-source implementation of Git written in pure Go. It is currently used for backing projects as a SQL interface for Git code repositories and providing encryption for Git.

The Dulwich implementation of Git is a pure Python software component for Python 2.7, 3.4 and 3.5.

The libgit2 implementation of Git is an ANSI C software library with no other dependencies, which can be built on multiple platforms, including Windows, Linux, macOS, and BSD. It has bindings for many programming languages, including Ruby, Python, and Haskell.

JS-Git is a JavaScript implementation of a subset of Git.

## Conventions
Git does not impose many restrictions on how it should be used, but some conventions are adopted in order to organize histories, especially those which require the cooperation of many contributors.

* The _master_ branch is created by default with _git init_ and is often used as the branch that other changes are merged into. Correspondingly, the default name of the upstream remote is _origin_ and so the name of the default remote branch is _origin/master_. The use of _master_ as the default branch name is not universally true. Repositories created in GitHub and GitLab will initialize with a _main_ branch instead of _master_.
* Pushed commits should usually not be overwritten, but should rather be \_revert\_ed (a commit is made on top which reverses the changes to an earlier commit). This prevents shared new commits based on shared commits from being invalid because the commit on which they are based does not exist in the remote. If the commits contain sensitive information, they should be removed, which involves a more complex procedure to rewrite history.
* The _git-flow_ workflow and naming conventions are often adopted to distinguish feature specific unstable histories (feature/*), unstable shared histories (develop), production ready histories (main), and emergency patches to released products (hotfix).
* _Pull requests_ are not a feature of git, but are commonly provided by git cloud services. A pull request is a request by one user to merge a branch of their repository fork into another repository sharing the same history (called the _upstream_ remote). The underlying function of a pull request is no different than that of an administrator of a repository pulling changes from another remote (the repository that is the source of the pull request). However, the pull request itself is a ticket managed by the hosting server which initiates scripts to perform these actions; it is not a feature of git SCM.

<!-- {{< figure src="https://raw.githubusercontent.com/wowchemy/wowchemy-hugo-modules/master/academic.png" title="The template is mobile first with a responsive design to ensure that your site looks stunning on every device." >}} -->
