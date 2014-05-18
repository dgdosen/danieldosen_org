--- 
layout: post
title: Hello danieldosen.org...
tags: 
- Personal
status: trash
type: post
published: true
meta: 
  _edit_last: "1"
  _wp_trash_meta_status: publish
  _wp_trash_meta_time: "1311534096"
  _wp_trash_meta_comments_status: a:4:{i:5;s:5:"trash";i:2;s:1:"1";i:6;s:5:"trash";i:7;s:5:"trash";}
---
Get three shells up and running!

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
