---
layout: post
title: "Create Me a Rails App"
date: 2011-09-26 20:18
published: true
comments: true
category: technical
---
I watched the latest and very helpful Railscast episode this morning - on [Spork](http://railscasts.com/episodes/285-spork) and wound up tweaking all the projects I'm working on to incorporate some of the things I learned in that screencast.

I also wound up tweaking a checklist I maintain in an Evernote entry of what I do to setup a Rails project.  Of the projects I'm working on, I wind up putting them all into a similar environment and figured it would be a useful blog post.  So here it is:

- Create a git repository: Git is pretty awesome.  If you don't care who sees your app, you can stick it up on Github for free! This is a no brainer.
    - [Github](http://github.com): Cheap and easy for a team of developers
    - Roll your own: I have a [Linode](http://linode.com) slice, and put up a private git repository
- Create a generic .gitignore file for the app.  Here's what I start with (on MacOS): 
    - .bundle
    - db/\*.sqlite3
    - log/\*.log
    - tmp/restart.txt
    - tmp/\*
    - .DS\_Store
    - public/system/documents\*
    - .sass-cache/\*
    - .powenv # I use [pow](http://pow.cx/)
- Use RVM: [RVM](http://beginrescueend.com) helps you manage multiple version of Rubies and related gem environments.  I try to use one rvm for all my "rails 3.1 apps that could end up on heroku" and call it `rails31`
    - Add a .rvmrc file to the root directory:  You should do this before you run `rails new` because you want to make sure you're using the version of ruby rails you want.  This means you should have a ruby and gemset created  already via rvm.
- Create the app: `rails new <app_name>` (I create so few apps, I always have to look this up - although now that I just wrote it in a blog entry, I'll probably never have to do it again.)
- Add the gems you want to work with.  I've always add a few to support BDD/TDD.
    - pg: Postgres is the default database on heroku, where most of my apps end up.  On top of that, I like the pg admin tool on mac os. Much more pleasant that mysql or using sqlite.
    - metric\_fu: Based on advice from the Railscast [Metrics, Metrics, Metrics](http://railscasts.com/episodes/252-metrics-metrics-metrics).  Simplecov is great.
    - formtastic: great for form processing
    - rspec-rails: I like RSpec over TestUnit
    - cucumber-rails: I also like BDD - even though it can be expensive in terms of time to run a test suite.
    - capybara
    - nokogiri: helpful with cucumber and capybara
    - factory\_girl\_rails: test factories
- Add gems for continous testing:  Rails 3.1 takes a few seconds to load - and I'd rather adopt tools that make it easy to re-run tests without delays:
    - database-cleaner: help with speeding up test runs
    - spork: a distributed ruby server environment
    - guard: supports continuous testing
    - guard-spork: helps to configure guard and spork
    - guard-rspec: helps to configure guard and rspec (don't forget the cli options :all\_on\_start =\> false)
    - guard-cucumber: helps to configure guard and cucumber
  rb-fsevent - a listener for guard
- Did you Check in yet?  Check in early and often
- Change your spec\_helper.rb file and move functionality up into the Spork pre fork block.
- Change your environment.rb to allow for factory girl and cucumber integration (of lots of borrowable step definitions)
{% highlight ruby %}

    require 'factory_girl/step_definitions'
{% endhighlight %}

- Create a database:
- Change your database.yml:

{% highlight haml %}
     adapter: postgresql
     database: <your_db_name>
     username: postgres
     password: <your_password>
     pool: 5
     timeout: 5000
     host: localhost
{% endhighlight %}

- Install RSpec

{% highlight ruby %}
    rails generate rspec:install
{% endhighlight %}

- Install Cucumber
{% highlight ruby %}
    rails generate cucumber:install --capybara --rspec --spork
{% endhighlight %}

- Add a model
- Migrate your database(s)

{% highlight ruby %}
    rake:db:create
    rake:db:migrate
    rake:db:test:prepare
{% endhighlight %}

- Make sure the site runs with one of your object controllers being the default home page configure everything for running tests quickly and automatically

{% highlight ruby %}
    # bootstrap spork
    spork --bootstrap
    # configure spec helper to use database cleaner
    guard init spork
    guard init rspec
    guard init cucumber
    # make sure spark block comes first
    # make sure rspec and cucumber both startup (in guard) with the --drb option
{% endhighlight %}

- Add a project in [Pivotal Tracker](http://www.pivotaltracker.com) (or some kanban tool) to manage your stories and velocity
    - I'm partial to pivotal tracker, it's much faster than your typical kanban tools
- BDD TDD in your features
- ...
- Profit!

Now this post doesn't really delve into configuration for most of these setup options, but there's a ton of great resources on the web.  Feel free to comment with your own indispensable configuration...
