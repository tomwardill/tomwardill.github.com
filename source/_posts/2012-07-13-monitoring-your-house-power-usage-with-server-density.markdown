---
layout: post
title: "Monitoring your house power usage with Server Density"
date: 2012-07-13 21:50
comments: true
categories: [Server Density, Power Usage, Current Cost]
---
A while back, I bought a [Current Cost Envi](http://www.currentcost.com/product-envi.html) power monitor for my house. Being something of a geek, I also bought the usb connecting cable. Unfortunately, the monitoring software provided is windows only, and not actually all that much use for monitoring over a period of time.

What we need is graphs. Lots of graphs.

My initial stab at this one was some [custom code](https://github.com/tomwardill/py-power-cost) that listened to the usb serial output, logged it to a local database then uploaded it to a remote server. This worked fine, but was a reasonably complex way of doing it. And I never quite got the graphs to work correctly.

Then I started working for [Server Density](http://www.serverdensity.com). We do server monitoring, and make graphs. The agent that does this can make plugins. The little gears in my mind started working overtime (Yes, it's actually pretty obvious what's coming, but hey...).

A condensed and simplified version of the listening daemon later, and I got this:

{% img media/images/housepower.jpg Power usage graph %}

A bit more playing around, and this was possible:

{% img media/images/housetemperature.jpg %}

So now I can see how warm my lounge is from anywhere in the world. Technology, it's great, ain't it?

How to make it work
-------------------

First, you'll need the code. That's on github.

   {% gist 3117465 PowerCost.py %}

Then you'll need step one and two from [this guide](http://support.serverdensity.com/knowledgebase/articles/76018-writing-a-plugin-linux-mac-and-freebsd)

Pop the plugin file into the directory you've set up, and name it PowerCost.py, and then restart your agent.
Then off you go.

Enjoy it, and remember, graphing thing is the way of life.