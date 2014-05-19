---
layout: post
title: Hello danieldosen.org...
tags:
- Personal
status: trash
type: post
published: true
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
