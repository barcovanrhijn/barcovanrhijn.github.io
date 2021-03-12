---
title: Image Converter
layout: post
author: Barco van Rhijn
category: Bash
---

I've been involved in an e-Commerce startup on and off for a few months and one recurring theme has been image optimization issues. 

Continually compressing images on the web-server is really slow. Doing it by hand is annoying.

And while we've seen and used some of the lovely API's that have been built. One blazingly obvious solution has been to enable Marketers making images to upload optimized images.

This solves issues with using images on multiple platforms. And not just the e-Commerce shopfront.

## Helping a Marketing team solve image compression

So I set out to build a simple tool. Started out in Python until I kept hitting slow conversion times due to the way the libraries run single threaded. 

Png to Jpg compression was also sub-optimal in the Python libraries I tried.

Image compression libraries in Python just don't have the raw speed you can get from something written in C++

So I moved to bash scripting, image magic and asynchronous execution. And started getting compression gains of 50% without significant quality loss. Compression times dropped from minutes to seconds. 

## Take Away
In the end I had a multi functional script that can:

- resize images for specific use cases
- tag on the correct meta
- compress 
- rename 

And manage to do it all in 1 - 2 options from a terminal. 

It literally took less time for marketers to learn the line of terminal than to teach them a UI. And for that they saved hours every week.

Plus I threw in SVG conversion as well saving Illustrators further time.

All in all the outcome has been overwhelmingly positive. And the site has never performed better. 

I pulled all the old images and converted them as a batch. 

## Future ideas
Building on what we've done here we can literally create an assembly line that runs with a cron-job. So files can be dropped into specific folders (network shares) and collected from an output folder later.

This would create the ultimate end user experience.

But we've come pretty close.
