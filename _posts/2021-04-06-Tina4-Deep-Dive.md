---
title: Tina4 we meet again
layout: post
author: Barco van Rhijn
category: Tina4
---

A number of years have passed since I first saw the [Tina4](https://tina4.com/documentation) stack. Tina4 officially strives not to be a framework. So rather call a collection of best practices for PHP but soon other languages as well. 

I recall the Manga graphics and names to different sections of the code back in 2014 when I first saw Tina4.

I've been working with Andre van Zuydam full time for the past 3 weeks. In this time I've gotten to know Tina4 toolset up close. 

One of the key things that I've found striking is that Tina4 does not abstract work unnecessarily by adding NPM scripts. There are some Composer scripts for most Tina4 tasks. Everything else is done either in the browser or in PHP. 
Of course if you want to do Ajax you'll need to write some JS. 
## What's included
Out of the box Tina4 includes quick ways to get you up and running in a lightweight way when you want to build a new PHP app. Its installable with Composer. 

Talking about includes. Tina4 makes in unnecessary to add include lines in any of your files.  

### Caching by default
Caching is included out the gate with PHP Fast Cache. There's no config required.

### SASS Support
No need to add extra build scripts unless you're building very complex SASS hierarchies. Drop you SASS in the SASS directory and run your APP. Your SASS builds to CSS without extra commandline tasks to manage.

### Migrations
Migrations in Tina4 are brought right back to SQL. It's been a pain point to me that many frameworks so abstract migrations that people forget that they are working with SQL.

In Tina4 you write your migrations in the browser which creates the required migration files that create a record in the migration database. Execute migrations by calling a migration endpoint in your browser. You see the output directly. Migration files are editable since they really only contain the SQL you entered the browser.
If you can write SQL you can do migrations immediately. This is a benefit that is easily overlooked unless you've felt the contortion caused by Frameworks that abstract migrations and other bits for the sake of abstraction. 

### ENV Support
Naturally any modern workflow needs ENV support out the box. 

### Routes
Routes can be written in different files as long as they are stored in the Routes directory even if they are sorted in subdirectories. This makes managing routes much simpler in practice. 

Routing in Tina4 is similar to what you'd get to know in Frameworks like Laravel. You should remember that Tina4 is a much lighter stack in kb not features. 

### ORM
The Tina4 ORM supports Firebird, Mysql, Sqlite right out the gate. So expect very similar syntax for each Database you interface with

If you write your database column names according to convention then you get to include very minimal information in an ORM class.

```
$firstName = "Bob"
$user = (new User())->select("*")
                    ->from("user")
                    ->where("first_name = {$firstName}")
                    ->asArray();
                    
```

### API
Consuming and generating API's are easy in Tina4. 

#### Consuming API
Tina4 Comes with API functions that make consuming rest endpoints as simple as can be. Even easier than using Javascript Fetch(). And you can still use JS Fetch if it catches your fancy.

#### Creating an API
Tina4 comes with a one line CRUD generator that you include in a new API endpoint file. Once you fire up the app in the browser Tina4 scaffolds all the crud routes for an ORM Object onto the API endpoint of your choice. 
One line of code, and your API works out the box. It's all still written in PHP.

ORM classes cleverly extends to CRUD routes that are widely used in Tina4 to create API's with a single line of code.
A CRUD route is linked to an ORM object, if you post a form containing inputs that match the ORM fields you don't need to write any code to create or update records.
This works so seamlessly that at first glance it almost feels like magic.

### Templates
Templates are elegantly integrated in Tina4 using Symphony's Twig template engine with some custom work where it matters. 

Templates can run without any routing if there is no route with the same name. This makes for convenient testing and less hassle when you have a route that really only serves up a page. 

### HTML Functions
Tina4 includes a library of php functions that can generate HTML right out the box. 

There's an underscored function for every HTML class imaginable. So you literally can generate valid HTML from code

### Admin Dashboard
Tina4CMS is probably the best kept secret when it comes to Tina4. It creates a fully functional Admin Dashboard with minimal lines of code. 
You get Templates and Crud Grids generated with create, edit, delete, search and export out the gate.

Login is included as well out the box to get your Admin Dash functional as soon as possible. With a little tweaking your Admin dashboard works exactly like you want it.

### Ajax
Tina4 comes with a JS helper library to post and get page parts, modals and more from api endpoints

## Conclusion
Simplicity is the ultimate complexity. Tina4 is a flexible and rapid starting point to any PHP project. As I've worked with it I'm fascinated by how simple Tina4 makes things that are often very complex in the PHP world. 

If you've been frustrated with how Frameworks abstract things away too far, Tina4 is a good place to invest your time. 
There's a Slack group where the community join in and ask and answer questions. Along with Documentation on how Tina4 works.

I've been contributing to expanding the documentation in the past 3weeks. 

I'll be posting some insights on the blog. So keep an eye for more on this soon.

