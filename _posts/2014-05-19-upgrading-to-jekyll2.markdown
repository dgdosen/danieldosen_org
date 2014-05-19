---
layout: post
title: "Upgrading to Jekyll 2"
description: "  "
categories: personal
tags: tech
---

I noticed that [Jekyll](http://jekyllrb.com/ "Jekyll"), the component used to
create this blog, has been upgraded to V2.0.
I'm particularly happy that it helps streamline the ability to use SASS and
CoffeeScript for static-content sites.  To me, there are a few features
that I want to use in any blog/static site, and I get all of that with
Jekyll.  Can't beat it.  So here's what this site is using. Feel free to copy it
 from [Github](https://github.com/dgdosen/danieldosen_org "danieldosen.org on
 github"):

* Editing posts in markdown via vim.
* Having a history of my posts in a repo... very powerful to collaborate and
leverage an audit trail.
* Easy to now use compass and
[bootstrap-sass](https://github.com/twbs/bootstrap-sass "bootstrap-sass") for a
generic, yet professional looking site.  I can even write some simple client
functionality to take advantage of some of the cooler bootstrap components.
* Easy to deploy with git hooks (you can't see that in the repo)
* Simple twitter/facebook/disqus integration
* ...
* Profit!

As an example of ease in configuration, here's my updated git config that lets me
deploy from my laptop, right to my public facing web server:

{% highlight INI %}

[core]
   repositoryformatversion = 0
   filemode = true
   bare = false
   logallrefupdates = true
   ignorecase = true
   precomposeunicode = true
[remote "origin"]
   url = git@github.com:dgdosen/danieldosen_org.git
   fetch = +refs/heads/*:refs/remotes/origin/*
[branch "master"]
   remote = origin
   merge = refs/heads/master
[remote "deployment"]
   url = your_deployer@your_website.com:~/repos/danieldosen_org.git
   fetch = +refs/heads/*:refs/remotes/deployment/*

{% endhighlight %}

In upgrading, I took a look around to see the infrastructure out there that supposedly helps
someone in using Jekyll, but as far as I'm concerned, they mostly seem to get in
the way:

* [jekyll-bootstrap](http://jekyllbootstrap.com/ "jekyll-bootstrap"): already
outdated and a bit byzantine...
* [octopress](http://octopress.org/ "octopress.org"): more outdated
* [generator-jekyll](https://github.com/robwierzbowski/generator-jekyllrb/
"generator-jekyll"): You  now get a nice workflow for building and monitoring
a site with jekyll... this just adds another level of complexity, and is
implemented in js.  I'd rather just keep it all in ruby... And it's now
outdated...

Now, all I have to do is generate interesting content.

Thoughts?
