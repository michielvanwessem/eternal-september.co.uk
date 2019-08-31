---
layout: post
cover: 'assets/images/cover3.jpg'
navigation: True
title: Running gogs inside a docker container
date: 2018-01-10 12:47:00
tags: sysadmin technical git
subclass: 'post tag-sysadmin tag-technical tag-git
logo: 'assets/images/ghost.png'
author: 'michiel'
categories: michiel 
---

I am becoming quite a fan of restraining services within docker containers. As many may know, my blog (running [ghost]() itself is running within a docker container with [nginx](https://nginx.com) in front of it as a reverse proxy.

One of the projects I really wanted to play with, was making a docker container for [gogs](https://gogs.io/), a git g server written in the [Go language](https://golang.org). 

I have played with gogs before, though only as a stand alone service. One of my last jobs at [Adaptive](https://adaptive.co.uk) was to implement an internal accessible git service that gave all the developers and support staff access to the keys repository. This was done as a service as previous the keys were given out as needed by the system administrator on a as/when needed basis.

The nice thing of deploying gogs in such an environment is that this meant that I could mirror with the original repository on the server, albeit with an eight hour delay. The mirroring service that Gogs has built in as one of their tools makes it very easy to set up a delayed mirror.

The reason why I deployed this? Because having a delayed mirror offers a small sense of reliability in case someone accidental wipes the repository or deletes a key. You can stop the delayed replication, fix the repository and move on from there.

But with my interest in docker, I wanted to actually see if I could get gogs running in a docker container. Why,


Git as a service? 

