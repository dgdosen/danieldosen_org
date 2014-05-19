---
layout: post
title: More Better Writing
tags:
- Personal
type: post
published: true
meta:
---

So, I'm back to posting. This is, what will be, one of my first blog posts in any blog for a long time. And just to set the record straight - every time I started to blog about anything, I never kept with it.

Now, however, I'm taking a different tack. Blogging can and should have a more powerful impact on what I'm doing and I've come to realize that blogging can have a positive impact on my life in a few ways:
<ul>
	<li>I want to write more to contribute to the Rails/Objective C world.</li>
	<li>I'd like to write more about data modeling and rails - if only to capture some of the cool things I've learned in the past year or two. Right now, all these little gems I've learned, or applied, are stuck in some Evernote notebook.</li>
	<li>I want to apply lean development practices to lean publishing (which is already a term I learned about this week at Seattle's Lean Camp.</li>
	<li>Blogging is the gateway drug to book-writing - which when it comes to something like ePub - there's no reason why the world doesn't need a book by Daniel Dosen - even if nobody or just a few read it. Now it's a goal of mine, so it will happen.</li>
	<li>…</li>
	<li>Profit</li>
	<li>I want to publicly commit do doing things like - updating or writing a gem. The main reason is, to me, I need more github based code with my name on it. Most everything I do or have, is in a private repository on github, or on my own git server at agidevelopment.com</li>
</ul>
Hey, look-y here - this is almost a blog post.

I have to admit, I've spent more time getting this blog set up than I did writing this post. And this is WordPress - One thing I'm particularly fascinated about is adding syntax highlighted code in a post - so here's something working with the WP-GeSHi-Highlight plug-in. It works, but I wish it supported markdown:
<p> </p>


{% highlight ruby %}
    class Pomodoro < ActiveRecord::Base

      belongs_to :activity

      attr_accessible :start_date_time,
        :length,
        :completed,
        :note,
        :location_id,
        :break_length,
        :activity,
        :activity_id,
        :activity_attributes

      validates_presence_of :start_date_time

    end
{% endhighlight %}
