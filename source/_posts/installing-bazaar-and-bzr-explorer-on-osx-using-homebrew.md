---
title: Installing Bazaar and bzr explorer on OSX using Homebrew
url: 210.html
id: 210
comments: false
categories:
  - Misc
date: 2012-10-19 12:47:28
tags:
---

Just about drove myself insane trying to figure out how to get bazaar explorer installed on OSX (running 10.6 Snow Leopard). I used home brew to install bzr and that worked fine, but then trying to get the explorer (which doesn't come bundled with the brew bzr version) was futile.

#### So here are the instructions (starting from scratch):

1.  [Install homebrew](http://mxcl.github.com/homebrew/)
2.  Install python: `brew install python`
3.  Install bzr: `brew install bzr`
4.  Install pyqt: `brew install pyqt` (it will also install dependancies)

That's the easy part - now for the bit I got stuck on:

1.  Download the [qbzr](http://wiki.bazaar.canonical.com/QBzr) and [bzr-explorer](https://launchpad.net/bzr-explorer/+download) binary packages
2.  Find the folder ~/.bazaar (in your User Home folder)
3.  Create a new folder called "plugins" if it's not there already
4.  Extract both the qbzr and bzr-explorer binary folders and then copy them to the plugins folder you just created
5.  Run - `bzr explorer`

As far as I can tell - because homebrew maps the bzr install to the proper directory everything that gets dumped in there should work as per normal. If this isn't the case for you it may pay to take a look at your [symlinks](http://cheat.errtheblog.com/s/brew/).