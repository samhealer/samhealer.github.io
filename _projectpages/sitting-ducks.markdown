---
title: "Sitting Ducks"
layout: project
year: "2023-02"
tag: sitting-ducks
<!-- image: assets/images/projects/skylark1.png -->
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "A static site generator for 1000 Tiny Birds"
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** February 2023\
**Tools used:** Go, Milligram.css

I thought it was about time to break the current trend of hack day projects which were a) music-based, a)i) Spotify playlist generation-based, to be precise, and b) Python-based. I'd also been thinking about an idea I'd had for a while. I've always tried to keep a note of all the culture I consume - films, music, gigs, etc. But it would be nice to do more with that. Around new year's, I had the thought of trying to write a little something about all of them. Not as a proper blog or anything, just as more my own way of remembering these things, what I experienced from them.

I thought about bundling it into this site, but I - to be honest- am not a fan of how I build this. It's a statically generated site using Jekyll, with some horrific number of opaque plugins, that seems awfully slow (14 seconds to build the site!). And I had lots of fun complicated ideas in mind for what I wanted my site to do. And, y'know, sometimes it's fun building your own thing.

And thus, keeping the Venn diagrams of projects which are named after birds, birds referenced in Radiohead songs, and birds which are an apt pun on the project itself. Sitting Ducks. (Static. Get it? Eh? Eh?) Every entry is written in markdown files with a YAML frontmatter, with a number of different metadata options per media type (e.g. album/artist/year for albums, season for TV shows, venue for gigs, etc.). 

This is now building [1000 Tiny Birds](http://1000tinybirds.com), a site which will (knock on wood) end up containing 200 words, give or take, on every book, restaurant, film, TV show, gig, non-gig, album, and misc other things I consume in 2023. With a few hundred entries already, it still generates immediately. There is no more complicated build process than syncing the resultant html files to a basic nginx server running on a Digital Ocean I've got going spare.

![sd1](/assets/images/projects/sittingducks1.png)

There's lots of fun using Go templates and struct composition and inheritance etc. etc., and I do partly wish I'd done it in Python for the sake of dynamic typing, but all in all, I do really enjoy writing Go, and it was nice getting back to that for the first time in quite a while. Now I just have to keep up the actual writing of entries. Ha.