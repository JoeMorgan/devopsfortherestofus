---
layout: post
title: Error Upgrading Boot2docker
author: joe_morgan
excerpt: ""
tags: [docker, devops, container, virtual container, upgrade, boot2docker, docker machine]
comments: true
---

I hadn't touched [Guapo](/guapo/ "Guapo") in awhile, and when I finally got a chance to start working on it again, low and behold there had been some major changes with Docker. Boot2docker has been largely supplanted by docker machine, which seems like a great move overall, but in trying to make the transition myself, I ran into a showstopper issue:

## Error getting IP address: Something went wrong running an SSH command! ##

Sufficiently vague for you? I mean, gotta love error messages that include the phrase "something went wrong".

<!--break-->

I spent a couple of hours wading through issues on Github before finally hitting pay dirt. While <a href="https://github.com/docker/toolbox/issues/139" target="_blank" title="Github - docker toolbox issue: Toolbox fails at quick-start step">this issue</a> doesn't expressly call out my error message (which may have something to do with how long it took for me to find), the solution works just the same: delete the default VM in Virtual Box.

Now, I wasn't really being very judicious, so I also deleted several other VMs. Mostly just the ones you get from <a href="https://dev.windows.com/en-us/microsoft-edge/tools/vms/mac/" target="_blank" title="Microsoft Edge Dev">Microsoft Edge Dev</a> (formerly modern.ie) for testing on old versions of Internet Explorer. So I can't say with 100% certainty which was the culprit. But I wanted to write this post in the event that it could save someone a couple hours of digging.

Happy upgrading!