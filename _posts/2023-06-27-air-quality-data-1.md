---
layout: post
title: "Air Quality Monitoring, Part 1"
description: "Can I build a tool to predict ground-level air quality from satellite measurements?"
date: 2023-06-27
feature_image: images/baltimore.jpg
tags: [air-quality, satellites]
---

A few weeks ago, I woke up to the worst air quality index ever seen in Baltimore, where I live. Wildfires in Canada had blown smoke down, resulting in an air quality index of over 200. That may not sound like a lot, particularly if you're from out west, but I've only ever experienced air quality that low in the center of Beijing. On a normal day, I can see the [Mount Vernon Washington Monument](https://en.wikipedia.org/wiki/Washington_Monument_(Baltimore)) in the distance on my commute to work. On that day though, I could barely see a few blocks. That got me thinking. 

I work with astronomical datasets for a living, and one of the issues we encounter is called [extinction](https://en.wikipedia.org/wiki/Extinction_(astronomy)). The principle behind extinction is fairly intuitive. Imagine we want to look at a star thats very far away from us in a telescope. First, that light needs to be emitted from the star. Then, the emitted light needs to travel from the star into our telescope. Sounds simple right? Not quite. Space is full of gigantic clouds of dust. Astronomers call it the interstellar medium, or ISM. That dust blocks some of the light from reaching us. It's kind of like trying to look across a room full of smoke: you can get a pretty good idea of what's on the other side, but you're not going to get a perfectly clear picture. In astronomy, this means that our observations aren't quite reality. Entire careers are built on making 3-dimensional maps of these dust clouds so that we can correct for extinction and get a clear image of what's on the other side of them.

But what, you may (reasonably) ask, does that have to do with bad air quality in Baltimore? Well, it turns out that extinction isn't unique to astronomers. You see, one of the most important sources of data in understanding air quality are satellite measurements. If you want to measure something on the Earth's surface from a satellite, you've first got to get through the atmosphere. And if you're observing something through the atmosphere, it's not gonna be the same as what you'd measure on the ground.

To zeroth order, the atmosphere acts a lot like one of these interstellar dust clouds, but there are two crucial differences. First, interstellar dust clouds are *very* spread out. That means that any given photon of light is less likely to hit a dust particle, which means that the final picture is going to have less extinction. The atmosphere, by contrast, is so dense that certain wavelengths of light never even make it to the surface. Practically speaking, this means that a lot of satellite measurements aren't actually measuring conditions on the Earth's surface, they're actually only measuring so far deep into the atmosphere.

The second factor is maybe even more important: interstellar dust clouds don't move. That means that we can map their structure and develop models to work backwards and figure out how bright an observation target actually is, since we know how bright it looks and how much dust is in the way. The atmosphere, obviously, does move. The consequences of this are what we call weather. If we wanted to develop an analogous algorithm to correct for extinction, we would need to have a perfect picture of the exact chemical and thermal distribution of the atmosphere at any given time. The existance of the field of meteorology is testament to the fact that that's impossible given current technologies ([and almost certainly the laws of physics!](https://en.wikipedia.org/wiki/Laplace%27s_demon#Thermodynamic_irreversibility)).

**So here's the problem:** satellite measurements of the key parameters that control air quality index, concentrations of PM2.5, NO<sub>2</sub>, and SO<sub>2</sub>, aren't accurate representations of what I, as a human who lives on the Earth's surface, breathe in. Can I build a tool to use meteorological data to predict surface-level air pollution from satellite data? Stay tuned. 




