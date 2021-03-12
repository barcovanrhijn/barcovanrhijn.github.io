---
title: Vanilla PHP
layout: post
author: Barco van Rhijn
category: PHP
---
A Senior PHP developer approached me about collaborating on a Vanilla PHP project. His requirement was for us to work according to his Php standard. 

## Our Goal
Build a [template engine]{https://github.com/barcovanrhijn/sitebuilder} and Cms that work together through an Api connection.

The idea was building template engine that could be easily filled out with details to generate brand sites. 

## Creating a Design System

I asked to do the front-end generating code. I was inspired by how Atomic Design systems worked and decided to build out a template engine with some overlapping features with Twigg. 

Since the requirements was that there be no dependencies I could not use Twigg or Handlebars or other such systems. 

The project consisted of three parts. 

1. A UI that was customer facing and centrally manages all the site information and links (similar to a CMS backend). 

2. Template builder which connects to the API and parses the Json into arrays and then outputs this in a template. 

3. The API defines several settings that makes the Customer facing builder allow simple UI configurations and style changes.

I discovered that some of what I wanted to do to make the template more flexible is known as Meta programming. I discussed ways we could free the data model by moving to JsON in MySQL or MongoDB. Because after the first few days it became apparent that each new change in the data model introduced heaps of new work on both ends.

Moving the data model into JSON would actually allow dynamic assignment of some properties like classes. And would make implementing new classes and design features fairly easy. Allowing us to focus on getting to optimal designs for the front-end and back in a quicker time-frame.

It became clear that we needed a single language between the two code bases. I was starting to see a lot of variable assignment where I would reference a property on the API and rename it entirely.

So I came up with some naming conventions for different UI parts along with their properties. After we agreed on naming that made sense to both of us I documented this on a Wiki I'd started for our project. This in turn helped standardise the language in code and made it flow like good poetry.

I've always loved the simplicity of DokuWiki for such use cases.

I also started to get the sense that some of the design should be driven from the front end as it would allow more page flexibility for the template. 

To fully enable this would require a more unlimited data model especially when it comes to how many rows and columns are involved in the final design.

## Meeting PHP Unit
In the process of doing the work I decided to learn how to build unit tests in PHP. 

I've just touched on the basics of doing this in Javascript after what I'd learned in FreeCodeCamp. But I'd not used this in PHP yet. 

In the past I'd mostly customized PHP code or written small Wordpress plugins which did not have enough code to make Unit tests a viable option. 

When I asked the developer I worked with it turned out that he had not used PHPUnit before so I was on my own with this. 

## Lessons learned

The project contributed valuable experience but the partnership was not well matched. 

When comparing notes I was producing 6 Months of output in 3 Weeks compared to the other dev's output. 

I was putting out more hours and my workflow was more productive. 

The structure of our agreement was a percentage based project partnership which does not support varying degrees of input very well.

I was teaching Git and local PHP setup techniques since he was still pushing changes through to a FTP live server to view changes to the code base making colaboration painfully slow. 

I do this gladly but was let down by the nature of our agreement.

For future projects I'd favor an hourly fee or fixed monthly fee.

## Wrap up

In 3 Weeks I coded up my Vanilla PHP and produced a minimum viable product as part of an attempt to partner up with Senior PHP developer. 

I had started with a blank canvas and PHP documentation and 5min worth of Sage advice on how we'd structure the app.

All in all the project could be refined a lot but I'm [pretty pleased with the outcome](https://github.com/barcovanrhijn/sitebuilder) given how short the development time-frame was. 

