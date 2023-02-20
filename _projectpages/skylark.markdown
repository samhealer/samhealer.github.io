---
title: "Skylark"
layout: project
year: "2019-07"
tag: magpie
image: assets/images/projects/skylark1.png
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "A tool to represent git repositories as chiptune music."
category: project
author: samhealer
externalLink: false
big: false
---

**Developed:** July 2019\
**Tools used:** Python, pretty-midi, FluidSynth

At HPE, one of our most enjoyable perks are our monthly hack days - around a couple of days each month to spend as we see fit. Sometimes we use it for learning, sometimes we use it for semi-work-related projects. But a lot of the time, I'm the kind of person who likes to push the limits of what "don't take the piss" means when it comes to hack days, and my favourite example of this is what I did in July 2019: Skylark.

Don't ask me why, but for some reason I reckoned you could probably represent a git repository as a piece of music, and for some other reason I reckoned that might be interesting. It's an exercise in mapping the attributes of one to the attributes of another, in some vaguely meaningful way. In git, I figured you had the following "outputs" from each git commit:

* SHA-1 hash
* List of files
* Author
* Timestamp

And that these needed mapping to the following melodic "inputs":

* Pitch
* Duration
* Harmony
* Velocity
* Instrumentation
* Tempo


A SHA-1 hash looks a little like this:

`2fd4e1c67a2d28fced849ee1bb76e7391b93eb12`

This is 160 bits of information, so let's split it up into 20 8-bit chunks (or, I suppose, bytes). Each of these bytes can be mapped to a single note like so:

![68648492_361239248141556_8522284295832731648_n](/assets/images/projects/skylark1.png)

I take the first 4 bits and map that to the pitch value of the note. In order to lazily ensure that the generated notes don't clash terribly, these pitch values are restricted to the pentatonic scale, a scale often used in education and improvisation because it's basically impossible for the notes to be disharmonic with each other. As the name would suggest, the pentatonic scale has 5 notes in an octave, so with 16 values, we can cover three octaves, C1-C4. The next two bits determines the harmony, and the final two bits determine the duration, as so:

| Bits | Harmony       | Duration  |
|------|---------------|-----------|
| 00   | None          | 1/16 note |
| 01   | None          | 1/8 note  |
| 10   | 2 notes above | 1/4 note  |
| 11   | 3 notes above | 1/2 note  |


Skylark uses [pretty-midi](https://github.com/craffel/pretty-midi) to write out a MIDI file for the generated melodies and [FluidSynth](http://www.fluidsynth.org/) to programatically synthesise the audio. Let's give that a go with a single commit:

 
<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888427966&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/initial-stab" title="Initial Stab" target="_blank" style="color: #cccccc; text-decoration: none;">Initial Stab</a></div>

Not bad! Not great, but not bad. Here's some accidental minimalism from when I tried expanding that out to each commit in the tree and had a bug where I just synthesised each commit on top of each other rather than in series:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888427957&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/accidental-minimalism" title="Accidental Minimalism" target="_blank" style="color: #cccccc; text-decoration: none;">Accidental Minimalism</a></div>


We've still got some more attributes to play with, though. Not all git commits are created equal - some are just updating a README, some are touching almost every file in the codebase (unfortunately). So let's change the velocity of the MIDI notes within each commit, normalised within some sane boundaries, by how many files are touched. 

Although sometimes I'd quite like it to not be the case, there's obviously quite a few of us in the team all contributing to the repo. Seems fair enough that each contributor should be a different instrument in the final piece. 

I also experimented with having the tempo of the piece being affected by the gap in time between commits, to represent the pace of work being done, the lulls, the rushes. But as nice an idea as that is, it turns out that musically speaking, disastrous. 

Finally, Skylark originally used a basic piano soundfont, but that was boring so I ended up using a [Super Mario World soundfont](http://web.archive.org/web/20110111173805/http://www.shakal.net/lunar/misc/soundfonts/) to make it more legit. Here's the finished product, run on our codebase at the time:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888428332&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/baas-prov" title="baas-prov" target="_blank" style="color: #cccccc; text-decoration: none;">baas-prov</a></div>

The results are quite fun, but I can't imagine they'll be selling on Bandcamp anytime soon. By their auto-generated nature, they don't hold the listener's attention for too long, but it scratched my perpetual itch of combining making music with writing code. And hey, this convincingly won the popular vote in the presentations, so at the very least I got an Amazon voucher out of it. All I got for [Magpie](/projectpages/magpie/) was a first class masters degree; I leave it as an exercise to the reader as to which was more valuable.
