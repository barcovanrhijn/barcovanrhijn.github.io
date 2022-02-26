---
title: How much JS is enough?
layout: post
author: Barco van Rhijn
category: FrontEnd
---
There's been a growing trend towards Front-end JS frameworks in the past years. I think these frameworks have their uses. 
But I don't think Frameworks like React, Vue and Angular always make sense for every project. For me it all comes down to simplicity and getting work out the door close to budget. 

In adopting VUE and REACT I've noticed that we're effectively doing in JS what a Back-end language like Python, PHP, Node or Ruby would do rather well. 
So effectively we're duplicating the role and relegating the back-end to an API with a Database connection.

So now we have routers and state etc all running in the front end. No matter how you spin it, running business logic in the front end is a bad idea. 
As a result you're going to need a bit of both on such a project to keep sensitive data out of your front-end code. On some projects this can make perfect sense.

Then we have the issue of State which becomes rather complex when you're trying to run a webserver in the browser. All of which is perfectly liable to drive you to more abstraction.

Then there's the issue of how heavy things become after a bit. So if you've been writing a bit of VUE or REACT you reach a point where there's too much JS to be practical.
So you need to render down to HTML on the Server side and then just bring in dynamic bits. So effectively you're using React and VUE as a backend and front-end language at that point.
Unless you're doing something rather special this is no different from using AJAX and a Back-end language. Except that you've now moved all your code into JS and added heaps of complexity into the mix.

So am I saying front-end frameworks are bad? Not necessarily, but you do have to consider the budget implications of writing more code to do the same thing. For me the benefits don't generally outweigh the cost of doing so just yet.

## When I'd use a front-end Framework
There are cases where a front-end framework makes complete sense. 

- You want a highly interactive site. 
- You're not concerned with how much data your end user will need on his mobile phone. React and Vue make API calls just a bout every second. So unless you're using GraphML you're going to run up bill for your end user for sure.
- You have a customer with a very large budget
- You have a very large team 

### Thoughts on VUE
I've used React but have come to enjoy the syntactic sugar Vue adds on top of all this. In my opinion it's the most approachable of the Front-end frameworks. 
It's ability to add interactivity in your code without taking over your codebase until unless a page's complexity warrants it, is a sure win.

## When I'd just drop in bits of JS for interactivity.
On an average project you may just need a little interactivity. Similar interactivity can be achieved with a little JS or Jquery or another JS library without making things more complex than they really need to be.

## Conclusion
Each project is different, but in the end it comes down to what makes sense. If you are able to keep things simple you can deliver more of what the client wants and spend less time driving yourself to Abstraction.