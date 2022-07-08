---
title: "Curlew"
layout: project
year: "2022"
tag: magpie
<!-- image: assets/images/projects/skylark1.png -->
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "An project to generate an 8 hour workday playlist tailored to your daily calendar"
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** May 2022\
**Tools used:** Python, Flask, Spotipy

It occurred to me that in this world of Zoom meetings, there's no reason why I can't listen to music during meetings. But I supposed that the same music wouldn't work all day. After all, my day back then (when I was an actual software engineer) might be all over the place, like this:

![c1](/assets/images/projects/curlew1.png)

Wouldn't it be great if you could have a Spotify playlist that you could just start at 9am and just leave running all day, and as you moved from meeting to meeting, it would adapt with the times? Well lose sleep no more! Curlew is here to fulfil all your 8 hour workday playlist needs.

Curlew is a web application that takes as input an iCal file representing your calendar and a set of rules for different meeting keywords. For example, with my 1:1 with my manager, I might want some quiet, soothing classical music. For coding time, I absolutely want music that sounds like the Trent Reznor and Atticus Ross score to The Social Network - the quintessential coding music. And for sprint demos, I want some loud hard house, if only to keep me awake. 

![c2](/assets/images/projects/curlew2.png)

A final input is an artist you'd like your day to sound like in the non-meeting parts of your day.

![c3](/assets/images/projects/curlew3.png)

The result is a playlist a little like the below. Note the Radiohead-like tracks quickly moving into Holst and Purcell about 45 minutes in, heading briefly back to acts like Pixies and Sonic Youth, before into Explosions In The Sky and Sigur Ros for coding. A cheekly little easter egg for my super important 1:1 with my VP, where I'm really going to want to pay attention - half an hour of John Cage's 4'33" - before keeping my eyes from drooping in sprint demos with some Calvin Harris and Skrillex. 

<iframe style="border-radius:12px" src="https://open.spotify.com/embed/playlist/1zKrJcBXrwNtXlfi8cceiO?utm_source=generator&theme=0" width="100%" height="380" frameBorder="0" allowfullscreen="" allow="autoplay; clipboard-write; encrypted-media; fullscreen; picture-in-picture"></iframe>

