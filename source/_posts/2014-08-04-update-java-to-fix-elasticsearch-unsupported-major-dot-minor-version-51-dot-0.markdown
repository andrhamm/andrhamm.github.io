---
layout: post
title: "Update Java to fix ElasticSearch \"Unsupported major.minor version 51.0\""
date: 2014-08-04 15:11:54 -0400
comments: true
categories:
- software
- development
---

When I went to install ElasticSearch with Homebrew on Mac OS X, I got the following error message when trying to start up ElasticSearch: `"Unsupported major.minor version 51.0"`. I found the experience kind of sucky, with a lot of misleading or generally unhelpful posts out there when Googling. So naturally I figured I'd add to the confusion. Here is how I solved the problem on my machine. <!-- more -->

Find out which version of Java you are using:

    java -version

This is probably 1.6 if you are on Mac OS X. That was my case, and I needed 1.7 for ElasticSearch.

See where your Java lives:

    which java

This is probably `/usr/bin/java` if you haven't monkied with your native install.

Download [JDK 1.7](http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html)

    http://www.oracle.com/technetwork/java/javase/downloads/jdk7-downloads-1880260.html

I restarted at this point but my symlink (`which java`) didn't update. It seems like kind of a shitty way to get what you want, but setting your `JAVA_HOME` environment variable will now point your scripts to the right version:

    export JAVA_HOME="`/usr/libexec/java_home -v '1.7*'`"

This sort of stuff seems to come up anytime you mention JDK or JVM being a dependency of anything. Sweet dice...
