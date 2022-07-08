---
title: "Nightowl"
layout: project
year: "2022"
tag: magpie
<!-- image: assets/images/projects/skylark1.png -->
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "An app to reduce the decision space for Spotify playlist creation through Tinder-like swiping"
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** June 2022\
**Tools used:** Dart, Flutter, Python, Flask, Spotipy

Another couple of months, another set of hack days. A few weeks before this, I was throwing a little get together at my house, and about five minutes before people started turning up, I thought "oh god, music, I need music" and in that moment completely forget every song that had ever existed. I looked at my library, but it felt overwhelming to pick songs I thought would work together. Two birds, one stone. And actually, I wanted an excuse to play with Flutter, so I guess three birds, one stone.

Thus, Nightowl, a multi-platform app that helps in playlist creation. Nightowl will randomly select songs from your Spotify library, presented to you in a Tinder stylee - swipe right to add it to your playlist, swipe left to skip it.


![no](/assets/images/projects/nightowl.jpg)

After you've added 10 songs to your playlist, Nightowl moves away from using existing songs from your library, to taking the average liveness, loudness, energy, and danceability and using those as seeds for Spotify's recommendation algorithm to help expand your playlist further. 

And that's it! I've nearly actually got it working for multiple users, so it might actually get released in some way. It's built as both a website and an Android app, with the backend running on a Digital Ocean instance. Not too bad for three days' work. 