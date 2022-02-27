---
title: How to solve Github Amnesia
layout: post
author: Barco van Rhijn
category: Git
---
If you work with any technology long enough you get to see some quirks. 
In the recent couple of months I've started seeing something that I can only term Github Amnesia.

Often when I push up code it goes MIA. In some cases I've seen code refuse to get marked as changed on a fresh Clone. In the end it became apparent that Origin had lost the plot.
So today I'll show you some strategies in dealing with this kind of thing. 

Most people are quite a bit confused when they first see this. Some Devs still live in denial of the fact. So when you ask around the office it's almost assumed that the issue cannot possibly be git or Github.  And So I thought I'd write something about this in the hope that it can be useful to others who reach equally perplixing stages of git.

## How it looks
- Commit the files. 
- Check that everything that's changed shows up. 
- Push confirm no errors are shown.

```bash
git commit
git push
```
### Confirm if the code is on Github
If it's still missing try the next step

### Add the files again with -f

```bash
git add -f path/to/file
git push
```

### Confirm if the code is on Github
Copy your code folder elsewhere temporarily
