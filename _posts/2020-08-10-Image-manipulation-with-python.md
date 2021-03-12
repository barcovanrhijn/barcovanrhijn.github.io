---
title: Image Manipulation with Python
layout: post
author: Barco van Rhijn
category: Python
---

So an e-Ccommerce project I'm working with has hit a new requirement to create bulk vouchers images for clients that can be sent out using social media. 

We set out to create a template and fill it out with a loop. 

I chose Python3 for the task. There are lots of libraries like Image Magic that have overlay systems. But this is done in Raster so the image will get re-compressed.

Then it hit me that SVG is really just an XML spec. And a great idea emerged. 

- Add template tags like {{ name }} in a text box in an SVG file. 
- Do a plain find and replace on the file. 
- Convert to PNG with ChairoSVG

## Wrap up
I ended up with a script that reads a template file and inserts fields from an Excel sheet. This can be extended further to run from within a PHP front end. But it works nicely as is.
