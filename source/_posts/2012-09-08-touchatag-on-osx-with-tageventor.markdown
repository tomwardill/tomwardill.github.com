---
layout: post
title: "Touchatag on OSX with tagEventor"
date: 2012-09-08 10:58
comments: true
categories: [RFID, OSX, touchatag, electronics]
---

I'm planning a talk on monitoring things that aren't servers. The physical realm is something we all interact with, but very rarely actually monitor.

Part of this involves a touchatag (tikitag) RFID reader, my laptop and an Oyster card.

The easiest way to do 'if this card turns up, do this' is some software called [tagEventor](http://code.google.com/p/tageventor/). A simple daemon that listen to the card, and will run a given script for a particular card.

Herein lies instructions on how to make it work on OSX (Mountain Lion in my case, but instructions should apply to most).

PCSCD
-----

This is the system daemon for talking to card readers. It's shipped with OSX and has the required dependencies. It needs a modification to the config to work with the Touchatag (as it ships with an unrecognised firmware).

    sudo vim /usr/libexec/SmartCardServices/drivers/ifd-ccid.bundle/Contents/Info.plist
    
    Change 
    <key>ifdDriverOptions</key>
    <string>0x0000</string>
    
    to
    
    <key>ifdDriverOptions</key>
    <string>0x0004</string>

And either restart the system or run the daemon manually with

    sudo /usr/sbin/pcscd -f
    
tagEventor
----------

Currently, the easiest way to get this is to build it from source, using [this github branch from bettse](https://github.com/bettse/tagEventor).

You will need XCode installed, as it's structured as an XCode project.

1. Clone the branch from github
2. Open the XCode project
3. Product > Build
4. In the left column in XCode, dropdown 'Products', right click tagEventor and select 'Show in Finder'
5. Copy the tagEventor binary to somewhere useful
6. In a terminal, cd to where you put the binary, and run `./tagEvent -v 3`

If everything is successful, you will see the output of tagEventor scroll by. If you don't, check that pcscd is running, and try testing that with `pcsctest`.

Once tagEventor is running, poke a rfid card at it (Oyster cards work), and you should see it detect the card and attempt to run a script. Remove the card and you should see similar output.

Create that script in whatever you're favoured language is, and it'll be executed with arguments when the card appears and leaves.

Enjoy your physical computer interface