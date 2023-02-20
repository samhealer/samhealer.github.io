---
title: "Roadrunner"
layout: project
year: "2021-01"
tag: magpie
<!-- image: assets/images/projects/skylark1.png -->
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "An app to sequence unique infinte pieces of music to soundtrack jogging"
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** January 2021\
**Tools used:** Java, Oboe (C++)

It's another hack day project! I've always (relatively speaking) been much more a fan of the treadmill - although [Trenchmill](/projectpages/trenchmill/) didn't help that - than running outdoors. I only started running outdoors during Lockdown 1, when it was all I really had available to me. I still didn't like it, and I just wasn't as good at it. I fell out of it until January, when we had a virtual charity race event at work that involved tracking your runs on Strava. So I gave it another go and realised that my pacing without a treadmill is *terrible* - I was running nearly twice as fast as I would be on a treadmill. No wonder I was only getting 10 minutes in and dying. I spent some time putting together a playlist of songs at the right tempo for me, and the next day I was knocking out a 5k like a champ.

Whilst I was going through my library to find songs with the right BPM, I realised that a track from the EP I released last year was the perfect tempo. After getting over the sheer arrogance of listening to your own music on a run, I put it on the playlist. But it got me thinking, it would be a fun challenge to compose a whole piece tailored to my run. That would get boring quickly, though. Then I thought, how about if I compose lots of small chunks of music, all still the same key and tempo, such that if shuffled it would still be a seamless piece. That sounded good, and could just be done with a playlist. But what if I went one layer deeper? What if you could vary the drums independently of the bass, and the bass independently of the melody, and so on. Even more infinite variations! But that's not gonna just work on a playlist now, is it. If only I could write code and had some time to spare for my own projects...

I wish there was more to tell you other than "I went away and did that", but really I went away and did that. [Oboe](https://github.com/google/oboe) is a very nice library in C++ for high-performance audio on Android, which is what I was looking for, given I was going to be playing multiple audio streams simultaneously that really shouldn't rush or drag from one another. I cobbled together an app that, every 16 bars, would pick and play one of a number of "chunks" from each available pool - a pool being, say "TR-909 drum machine" or "Lead piano". I quickly knocked together some of these chunks for demo purposes, and a short sample capture can be heard below:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/1000405069&color=%23ff5500&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/roadrunner-capture" title="Roadrunner Capture" target="_blank" style="color: #cccccc; text-decoration: none;">Roadrunner Capture</a></div>

It's not the most exciting piece of music in the world. I still need to compose more variations, which would also make for a future addition to Roadrunner - every 0.5km or 1km, transition to a different "section" of the 5km piece. But hey, it's something to listen to.

Oh, the name! I always find myself naming my coding/music projects after birds with some relevance the the project at hand - [Magpie](/projectpages/magpie/) and [Skylark](/projectpages/skylark/) are both named for Radiohead lyrics (obviously). You have no idea how delighted I was when Roadrunner came into my head.