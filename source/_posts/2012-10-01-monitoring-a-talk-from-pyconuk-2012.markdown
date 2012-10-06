---
layout: post
title: "Monitoring - A talk from PyConUK 2012"
date: 2012-10-01 20:05
comments: true
categories: [Monitoring, PyConUK, Talk]
---

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.001.jpg 350 350 Slide 1 %}

This is a write up of a talk that I gave at PyConUK 2012. It seemed to go pretty well, though it's not hugely technical. If you were there, I hope you enjoyed it, if you weren't, I hope you find this write up interesting.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.002.jpg 350 350 Slide 2 %}

Given that work were paying for me to be there, I had to get at least one plug in; though there is a point to this slide.

Server Monitoring is easy, the tools exist and are plug and play now. Install the monitoring agent of your choice: [we do a very nice solution](http://www.serverdensity.com) and away you go.

It's perhaps time to see if we can move the techniques and software developed for monitoring server hardware and move them to monitoring things that aren't servers.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.003.jpg 350 350 Slide 3 %}

Heh.

Always say just the one thing controversial in any presentation. This one is mine.

While it's not meant entirely literally, there's a part truth in this. Starting development seems like a lot of slog to get to making a small dot moving around the screen. Everyone wants to make Quake (or the equivalent), and would prefer not to go through the boring stages of making the early stages.

Personally, I find hardware more impressive from the outset. A flashing LED that I've wired together isn't technically much harder than 'Hello World', but it certainly feels like I've acheived more. Perhaps this can be used to introduce kids to programming, rather than the current pure-software approaches.

One of the themes of this talk is that the current state of electronics has never been easier or cheaper. Software is boring, but hardware is impressive.

So, not entirely true, but I hope you can understand my point.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.004.jpg 350 350 Slide 4 %}

This slide is fairly obvious, except that there are two meanings to 'cheap'.
Obviously python is free, so monetarily it is cheap. The other meaning ties into the Library Support, there is so much python in existence, that there are usually multiple libraries for the same problem.
This makes it cheap to change between them, if you try a library and don't get on with it, throw it out and choose another.

External Dependencies is important, python is 'batteries included', it tends to ship with pretty much everything you'd require to get started. The core library has modules for a lot of stuff.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.005.jpg 350 350 Slide 5 %}

Yep, that's fairly obvious. There's a bunch of stuff that I can't think of, and haven't seen. There's a lot of people out there doing this type of thing at the minute, so it's getting easier every time.

## Things you can monitor - a non-exhaustive list

There's not much I can say about these other than the contents of the slides, so SLIDES AWAY.


{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.006.jpg 350 350 Slide 6 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.007.jpg 350 350 Slide 7 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.008.jpg 350 350 Slide 8 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.009.jpg 350 350 Slide 9 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.010.jpg 350 350 Slide 10 %}

## Monitoring

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.011.jpg 350 350 Slide 11 %}

The most common types of data that you will encounter in monitoring is the float, closely followed by the boolean. Number of times the cat has left the house today, and is the cat currently in the house?

Time is important, any instantaneous time measurement can be treated as a time series, given a longer scale.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.012.jpg 350 350 Slide 12 %}

Accurate time is the most important thing, particularly if you are monitoring many disparate things. Without an accurate and joint time base to compare everything against, you'll end up doing a lot of work to shift the timebase to something useful.

## How to do it

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.013.jpg 350 350 Slide 13 %} 

These are the two most effective tools you can have. A Raspberry Pi and an Arduino. The difference have been talked about many times, so I won't go over them.
Short story, the Pi is more independent, the Arduino has better inputs and currently a better ecosystem around it.

There is however, nothing stopping you strapping an Ardunio to a Pi and having the best of both worlds (but doubling the cost of whatever project you have).

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.014.jpg 350 350 Slide 14 %}

This is some code. It's fairly simple code, mostly taken from the example and demos of two projects. Given a Garmin Heart Rate Monitor, an ANT+ usb stick, a Raspberry Pi and a 100mA gauge, this will display your Heart Rate on the console, and on the gauge.

Simple project that took me a couple of hours to put together, starting with nothing but the bits. Wiring this into some form of monitoring / graphing website would be equally straightforward.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.015.jpg 350 350 Slide 15 %}

Host software.

Take Data. Make Graph.

Also, the question that started this was 'can you graph your git commits against your heart rate, work out which bug annoyed you the most, and how many cups of tea it took to solve?'
The graph is most of the answer. It's something I built for a [hackday](http://www.leedshack.com) using the Heart Rate monitoring from above. It's my git commits on the project against my heart rate at the time. It kind of worked, you can see where I got up to walk around and where I was at my most calm.

## Things you can use

Again, non-exhaustive, but stuff I've found that's cheap and easy. Most of it's fairly obvious.

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.016.jpg 350 350 Slide 16 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.017.jpg 350 350 Slide 17 %}
{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.018.jpg 350 350 Slide 18 %}

## Feedback of Monitoring

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.019.jpg 350 350 Slide 19 %}

Lots of ways of getting feedback from your monitoring. Lights, sounds and graphs are pretty easy to do, that type of thing is pretty much a solved problem with regards to server monitoring, so just hijack that and use it for whatever else you can feed into it.

Of course, THE INTERNETS is your easiest method, Twitter, emails, anything like that has an api and a library to interact with it in python.

<br />
<br />

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.020.jpg 350 350 Slide 20 %}

Well, not quite monitoring. But it is a twitter controlled colour changing tent built from a RaspberryPi and some Dioder units from IKEA. From the minds of [Mike](http://twitter.com/mikechislett) and [Nathan](http://twitter.com/user_4574).

## Costs

{% img https://github.com/tomwardill/tomwardill.github.com/raw/source/source/media/images/monitoring/Monitoring.021.jpg 350 350 Slide 21 %}

Yup, quite cheap really. Not penny sweets cheap, but this stuff is all commercially available, and consumer grade. Easy to pick up off the shelf.

## The End

So that's the end, I hope it's been a worthwhile read.

Monitor everything, you never know when or where the data might be useful.

[@tomwardill](http://twitter.com/tomwardill) if you have any comments or suggestions.