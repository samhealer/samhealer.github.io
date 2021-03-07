---
title: "Magpie"
layout: project
year: "2016"
tag: magpie
image: https://sergiokopplin.github.io/indigo/assets/images/jekyll-logo-light-solid.png
headerImage: false
projects: true
hidden: true # don't count this post in blog pagination
description: "A system for automatic plagiarism detection in MIDI files"
category: project
author: samhealer
externalLink: false
big: true
---

![68648492_361239248141556_8522284295832731648_n](/assets/images/projects/magpie1.png)

**Developed:** Masters dissertation, January 2016 - May 2016\
**Tools used:** Python, Django, Javascript, tone.js


In the world of music, intentionally or unintentionally copying someone else’s melody can carry an ex- traordinarily large price tag, yet it is practically impossible to check this properly in a thorough manner. To solve this problem, I created Magpie, a system designed to automatically detect plagiarism in MIDI files.
The principal aim in designing Magpie was to be able to query a melody against a large dataset in an efficient and accurate manner. Inherent in this was a number of requirements, from implementing a data structure or algorithm which allows nearest neighbour querying against a large dataset quickly, to determining some way of ensuring that the comparison used to determine the distance between two melodies truly reflected how different they actually sounded, not just some absolute numerical distance.

The MIDI file format is incredibly expressive, but the trade off is a complicated file format which does not provide an easy way to access the key information; in order to meet the efficiency required, a simpler representation of the melody would be required. Finally, there needed to be a user-friendly interface to interact the system, which had to retain the speed and accuracy of the core implementation.

My primary contributions were:
* I researched the MIDI file format to determine exactly what information was needed and in what form it existed.
* I designed a new way of representing the melody which required less space, was more easily parsable, and was both pitch and tempo invariant.
* I wrote 4000 lines of code in Python to determine which track in a MIDI file was the vocal track, extract the melody, and convert the melody to my representation.
* I optimised an implementation of locality-sensitive hashing to be able to make a query against ∼ 400000 items in a dataset in a hundredth of a second.
* I created a mapping of numeric distance to harmonic distance in order to implement an improved distance metric for comparing two melodies, which takes into account musical similarity.
* I implemented a web-based front end for the system with an interactive piano roll to allow users to draw in a melody.