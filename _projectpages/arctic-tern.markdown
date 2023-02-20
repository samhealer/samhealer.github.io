---
title: "Arctic Tern"
layout: project
year: "2022-08"
tag: arctic-tern
<!-- image: assets/images/projects/skylark1.png -->
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "A project to design the perfect velocity-mapped Spotify playlist based on aggregated Strava activities"
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** August 2022\
**Tools used:** Python, Flask, Spotipy, Matplotlib

Another set of hack days, another project probably involving music. These ones crept up on me, and I hadn't really thought much ahead as to what I was going to do. I was more pre-occupied by the fact that in a few weeks' time, I was going to be running the Bristol 10k. Understandably, these two came to a head. 

The thought process this time, then: take the Spotify API; take the Strava API; smash them together somehow. I thought it would be fun to make my ideal running playlist. Strava activities track your pace to quite an impressive resolution (device-dependent, but I think I had a resolution of about 10,000 data points a minute?), so if I could use that to make a playlist that would have a roughly correct BPM for whatever my pace would be expected to be as it shifts over the course of a normal run.

There was no good Strava Python SDK, so I was hand-crafting my own API requests - always a pleasure. But the API was relatively straightforward and I wasn't doing too much with it - grab your activities, and filter by a user-specified distance (e.g. only consider runs of 5km or more) and type (e.g. run, cycle, kayaking). 

![at1](/assets/images/projects/arctictern1.png)

The user then gets to pick which ones they want to work with. For each of those, grab the velocity data and use that to come up with the average velocity map of a run, doing some binning by the average length of a song.

![at2](/assets/images/projects/arctictern2.png)

I'd already done the drawn out process of making playlists of songs that I liked that were all in my rough target BPM range, but my typical approach is just to pop those on shuffle and crack on. In this case, though, I wanted an order. The user gets to choose from their playlists which ones should be used as source material for the generated playlist. Luckily, when I did [Curlew](/projectpages/curlew/) and [NightOwl](/projectpages/nightowl/), I wrote all my Spotify code in a nicely extricable manner, so I had a library ready to go.

![at3](/assets/images/projects/arctictern3.png)

All these songs then get their BPM normalised to the velocity range (some actual maths going on there, exciting) and then the velocity bins are iterated through to find the track whose BPM most closely matches that portion of the run's pace. Pop that on a playlist, and job's a good 'un.

I think I promised in the sharing session to use that playlist for the actual Bristol 10k if people sponsored me. In the end, I think I tailored it a bit, but I deemed it overall a success and still raised like £250 or something. So all in a successful hack days. 
