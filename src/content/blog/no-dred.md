---
title: "No dred"
description: "Decided to stop using node red"
pubDate: "Mar 12 2026"
heroImage: "/blog-placeholder-5.jpg"
---

Been using nodered for a while but recently moved away. 
Dont get me wrong, it has a purpose and it does it very well. 
Just a few things that dont fit anymore. 

First project

![Thermometer](/images/thermometer.png)

This is to read a sonoff temperature sensor and pass it thru to homekit. 
Easy solution is the zigbee to matter gateway i have. Except it didnt work.
Presumably, someone decided the sensor was sending messages to quickly and decided to slow it down.
They introduced a delay which only held back the messages for a while and then burped them all out.
This caused the receiver to time out and assume the sensor was offline. 
Then choked it with messages. Sometimes it came back.

Nodered fixed this.  

The Main bridge is a plugin for Nodered that talks to zigbee2mqtt. 
The temp sensor is the actual device that gets passed thru a function and then on to homekit.
There is a plugin for homekit as well. 

There are a number of logical functions available in Nodered for reformatting messages etc, but
I found it easier to just write a few lines aof javascript.

![javascript](/images/javascript.png)

Big problem with Nodered is it is difficult to tell what the sender is sending (debug helps here)
or what the receiver is expecting. In one case i had to examine the source code of the plugin. 

Solution

Ikea released a matter based temperature sensor which sells for about 1/2 the price of the sonoff.

Moved on
