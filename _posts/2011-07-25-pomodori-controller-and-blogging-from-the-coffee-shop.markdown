--- 
layout: post
title: Pomodori Controller and Blogging from the coffee shop...
tags: 
- Personal
status: publish
type: post
published: true
meta: {}

---
- in the coffee shop
- not using their sucky bandwidth
- using personal hotspot
- ...
- profit

{% highlight ruby %}
  def create
    respond_to do |format|
      format.json {
        @activity =  Activity.find(params[:activity_id])
        # validate that this user is the current user...
        @user =  @activity.user
        @pomodoro = Pomodoro.new(params[:pomodoro])
        @pomodoro.activity = @activity

        respond_to do |format|
          if @pomodoro.save
            render json: @activity, status: :created, location: @activity
          else
            render json: @activity.errors, status: :unprocessable_entity
          end
        end

      }
    end
  end
{% endhighlight %}


Updating a new controller in pomodoro service that works on existing activities.  No reason to nest this under the user, as the user can be gotten from the activity. That means that you need to verify the current user is the user making the json call.
