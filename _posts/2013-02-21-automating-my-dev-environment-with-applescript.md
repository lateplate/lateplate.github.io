---
layout: default
title: Automating My Dev Environment With AppleScript
---
The [Starter League](http://starterleague.com) Winter 2013 quarter is in high gear, so I've been working on a number of projects simultaneously.

This requires a lot of context switching. Manually navigating around became a big waste of time, so I automated a few repetitive actions:

1. Opening a directory in Sublime
1. Opening a directory in iTerm
1. Opening a localhost URL in Chrome

I pieced together an AppleScript that does all of that for me. I simply set two paths in the script (file and URL), and the script does the rest. 

I've made multiple versions, one that opens up the right environment for each project. I never have to open those apps manually again.

You can [clone the AppleScript from Github](https://github.com/lateplate/dev-environment-automation-scripts/blob/master/open-dev-env.applescript), change those two paths, and start saving yourself some time.

(You can get crazy with it too - open Bash scripts, start Jekyll servers, open CodeKit, etc.)