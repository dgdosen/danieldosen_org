---
layout: post
title: "MVCs Galore"
date: 2011-09-26 01:05
comments: true
categories:
- technical
---

I just wrapped up a project (well, the first phase of a project) using [Microsoft's MVC3](http://www.asp.net/mvc/mvc3) framework for a client here in Seattle.  Similar to other clients I've worked with, they're a Microsoft shop and have an existing investment in the MS stack for building applications.  They wanted to leverage that investment on this project.

Working with MVC3 was pretty cool in that I had a different perspective of using Rails(Ruby) and Django/AppEngine(Python).  So, now I have perspective on using MS MVC3 I figure I'd share it with you.  Feel free to comment.

First - some things I liked about using MS MVC3:

- Visual Studio Intellisense - If you're going to use MS technology, you need to use those tools, and Visual Studio is great in its implementation of Intellisense.  It makes it easy to code and build your app. There's even Intellisense in Razor - the MS MVC equivalent to erb.
- Visual Studio Debugging - Another great way to leverage the tools to step in, add watches, and examine what's going on in your app while the server is doing its thing.
- The Entity Framework - I'll admit, I used to work on that team, so I'm impartial (Don't worry, everything I worked on is well hidden).  I like EF and where it's going.  If you're staring with a DB from scratch, the EF has some nice tools integrated within Visual Studio that makes it easy to get up and running.
- Nugets: They're the VS way to manage things like Gems inside a project.  There's really no equivalent to RVM/VirtualEnv as it just makes sure everything is up to date - but the Nuget management made it easy to add functionality form the MVC3/.Net ecosystem.

Some things I didn't like about MVC3:

- Migrations.   Wow - I'm spoiled by Rails Migrations.  They are essential when working with a team of developers.  They help make it blood simple to let any one developer catch up with database changes on their own terms.  I can't remember how I lived without them.  Even Objective C on iOS has their Core Data Migration capabilities.  MVC3 does not.  That's painful.
- ViewModelClasses.  That's right, Models, just for the views.   You already define your models, but say you want to pass a few things to a view, you should create a ViewModel Class to create strong typing of that data when you get painting those views.  Sure it makes you think about what your sending to the view, but it just feels unproductive to me.  With rails, you just create an @instance variable and you're ready to go.  Much simpler, IMO.
- Crashes.  Visual Studio crashes alot (this is on a mid2010 MacBookPro.)  Bootcamp and Windows7 run great, but Visual Studio just crashes from time to time.  It's a very heavyweight stack.  Compare that to VIM, which I use for everything these days, and it's a letdown.  It's the price you pay for that Intellisense.  I'll chose the VIM plugins any day.
- The ecosystem.  Between Github and Stackoverflow, I can overcome any issue I have with a Rails app, usually in a manner of seconds.  The wealth of information at your fingertips is awesome.  The community works.  With MVC3, there's MSDN forums, but I found myself using Stackoverflow more often that not, and when I did, it was a bit of an echo chamber.  The ability to execute within the open world of Rails just seems to move at a faster pace to me.  For example, Rails just implemented CoffeeScript.  With MVC3, you can, but it took some hunting, and there's only a couple of Google links that get you to the Web Workbench tools.  Or Testing.  Sure there's NUnit and Microsoft Test, but I kind of like RSpec's matching language, and all the BDD/TDD goodness you can get from using RSpec and Cucumber together.  It just seems like tools can get introduced, get developed and mature faster in the open source world.  

On that last point, I was talking about this with my client today.  The "open" world is just getting faster and better and I don't see how MS can keep pace unless they change the way they do things.  Add to that the cost savings (bring your best  TCO argument) of the non-MS environment, and I know what I'd choose, I'm just happy their's a choice.
