---
title: Delving into TypeScript - first impressions
layout: post
author: Barco van Rhijn
category: TypeScript
---
I discovered recently that Ionic have made VueJs quite a priority on their development line-up. And since I've got a new project lined up I decided to dig in and see what they've got. 

I've always liked the concise syntax to VueJs over ReactJs so I decided to give the two a go together.

Some early previews of the app working with working API intergration.
![alt Work Picking Screen](assets/images/picking-screen.png)
![alt Work Overview](assets/images/screenshot_2021-01-18-app.png)

## Ionic Vue comes with TS
So with VueJS and Ionic came a recommendation to keep Typescript. And so my journey began Mid Jan 2021 with types. 

It's not been all love at first bite but after delving into a 60min crash course I've been able to survive the first few days. The promised gains seem worth the pain.

My first few days have come with intense pain though. After coding for a few days I kept running into Type errors that I did not quite know how to solve. 

Initially it seemed that TS is the roadblock to getting any code to work. I'd write out perfect JS and it would fall on it's face every time. Test it outside of TS and it works flawlessly. 

And after spending a few days chasing Type errors I decided to dig deeper as there has to be something I missed initially. 

## A few lessons learned

### Run-time errors with TS and Ionic sometimes show skewed line numbers. 
This seems to be a current bug relating to SFC in VueJS. My Temporary work around has been to code with hot reload and fix errors immediately before proceeding. It's a better way of coding that leads to better productivity any way. 

### Git is your friend
When line numbers go fuzzy and minutes go by. It's often easier to revert a small change and start it again. Since we've got git might as well put it to good use.

### Types are easy
The fundamentals of Types are not hard. But you need to give you brain some time to absorb the implications in code. 

Most of TS is really just JS and you can actually partially implement TS in a project.

Essentially Types are a way of documenting expected data types and values for
- variables
- arrays 
- objects. 

There's much debate around this but the simplest way is that you should only use Interfaces for Objects. For all the rest use type definitions.

### Bypass Types in a pinch
In a pinch you can define the type as Any. But this should be used with caution as it sort of negates the benefits of using TS in the first place.

## Sage Advice
As a Senior Ionic Dev pointed out types are mostly inferred in Ionic and you'll run into type issues if you're trying to do something too radical.

## Wrap it up
Looking forward to seeing how TS will improve my development experience. I already enjoy the variable hinting TS introduces in VS Code. 






