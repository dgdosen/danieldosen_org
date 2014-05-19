---
layout: post
title: Round-tripping code posts with MarsEdit - Not Pretty
tags: []
status: publish
type: post
published: true
---

Trying out MarsEdit and posting...

Using the square brackets when publishing an entry via mars edit  is pretty fragile. The best bet is to just use simple pre tags, as is the case with the default version of WP Syntax Highlighter.  Then you just turn off the toolbar, which doesn't work well anyway.

{% highlight ruby %}
      describe "POST create" do
        # test code roundtripping with marsedit
        it "should create a pomodoro from json" do
          post :create, :format => "json", :activity_id => @activity.id, :pomodoro => {
            "start_date_time" => "2011-07-22 00:00",
            "length" => "25",
            "completed" => "0",
            "note" => "json post individual pomodoro",
            "break_length" => "5"
          }
          pomodoro = assigns(:pomodoro)
          pomodoro.id.should > 0
          pomodoro.note.should == "json post individual pomodoro"
          pomodoro.length.should == 25
        end
      end
{% endhighlight %}


It looks to me, like you'll need to do more of this before posting… Just don't edit a post (or round trip it) in Mars Edit
