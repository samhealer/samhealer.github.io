---
title: "Skylark"
layout: post
year: "2019"
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

(a more in-depth exploration of Skylark is available in [this blog post](/2019/07/31/skylark))

**Developed:** July 2019\
**Tools used:** Python, pretty-midi, FluidSynth

At HPE, one of our most enjoyable perks are our monthly hack days - a couple of days each month to spend as we see fit. At the end, we present to everyone else what we've done, and have a vote on the popular favourite. Sometimes we use it for learning, sometimes we use it for semi-work-related projects. But a lot of the time, I'm the kind of person who likes to push the limits of what "don't take the piss" means when it comes to hack days, and my favourite example of this is what I did in July 2019: Skylark.

Don't ask me why, but for some reason I reckoned you could probably represent a git repository as a piece of music, and for some other reason I reckoned that might be interesting. It's an exercise in mapping the attributes of one to the attributes of another, in some vaguely meaningful way. Skylark takes these attributes from each commit in the git history for a given repo, and translates them to the following properties of a piece of music


| Attribute of a git commit     | Attribute of a melody/note                    |
|-------------------------------|-----------------------------------------------|
| SHA-1 hash                    | Note pitch, duration, harmony                 |
| List of files                 | Velocity                                      |
| Author                        | Instrument/voice                              |
| Timestamp                     | Tempo                                         |


Skylark uses [pretty-midi](https://github.com/craffel/pretty-midi) to write out a MIDI file for the generated melodies and [FluidSynth](http://www.fluidsynth.org/) to programatically synthesise the audio. It originally used a basic piano soundfont, but that was boring so I ended up using a [Super Mario World soundfont](http://web.archive.org/web/20110111173805/http://www.shakal.net/lunar/misc/soundfonts/) to make it more legit.

The results (below) are quite fun, but I can't imagine they'll be selling on Bandcamp anytime soon. By their auto-generated nature, they don't hold the listener's attention for too long, but it scratched my perpetual itch of combining making music with writing code. And hey, this convincingly won the popular vote in the presentations, so at the very least I got an Amazon voucher out of it. All I got for [Magpie](http://localhost:4000/projectpages/magpie/) was a first class masters degree; I leave it as an exercise to the reader as to which was more valuable.

#### Samples

The day job's git repository in chiptune stylee:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888428332&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/baas-prov" title="baas-prov" target="_blank" style="color: #cccccc; text-decoration: none;">baas-prov</a></div>

An initial test of a single git commit, only translating the SHA-1 hash to pitch, duration, and harmony:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888427966&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/initial-stab" title="Initial Stab" target="_blank" style="color: #cccccc; text-decoration: none;">Initial Stab</a></div>

An accidental minimalist piece created when accidentally synthesising each git commit's melody in parallel rather than in series:

<iframe width="100%" height="166" scrolling="no" frameborder="no" allow="autoplay" src="https://w.soundcloud.com/player/?url=https%3A//api.soundcloud.com/tracks/888427957&color=%23ff9900&auto_play=false&hide_related=false&show_comments=true&show_user=true&show_reposts=false&show_teaser=true"></iframe><div style="font-size: 10px; color: #cccccc;line-break: anywhere;word-break: normal;overflow: hidden;white-space: nowrap;text-overflow: ellipsis; font-family: Interstate,Lucida Grande,Lucida Sans Unicode,Lucida Sans,Garuda,Verdana,Tahoma,sans-serif;font-weight: 100;"><a href="https://soundcloud.com/samhealer" title="samhealer" target="_blank" style="color: #cccccc; text-decoration: none;">samhealer</a> · <a href="https://soundcloud.com/samhealer/accidental-minimalism" title="Accidental Minimalism" target="_blank" style="color: #cccccc; text-decoration: none;">Accidental Minimalism</a></div>

