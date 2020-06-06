---
layout: post
title:      "Setting up a Sinatra App"
date:       2020-06-06 01:54:30 +0000
permalink:  setting_up_a_sinatra_app
---

Originally posted <a href="https://dev.to/sincerelybrittany/day-5-100daysofcode-setting-up-a-sinatra-app-3nn9"> here </a> and all future post will be on <a href"https://dev.to/sincerelybrittany"> my personal dev.to blog </a> -- please follow me for more content. 

Something I struggle with is setting up my text editor/app with the correct file structure to proceed with a project. Sometimes you dont need all the information given in running <a href="https://guides.rubyonrails.org/getting_started.html"> ``rails new APP_Path`` </a> and I was given the following templates -- <a href="https://github.com/thebrianemory/corneal"> corneal </a> and <a href="https://github.com/c7/hazel"> Hazel </a> -- that do come in handy, but sometimes you just want to build it yourself. 

Directory structure:
```
├── config.ru
├── Gemfile
├── Gemfile.lock
├── Rakefile
├── README
├──── app
│   ├──── controllers
│   │   └──── application_controller.rb
│   ├──── models
│   └──── views
│       ├──── layout.erb
│       └──── index.erb
├──── config
│   ├──── initializers
│   └──── environment.rb
├──── db
│   ├──── migrate
│   └──── seeds.rb
├──── lib
│   └──── .gitkeep
└──── public
|   ├──── images
|   ├──── javascripts
|   └──── stylesheets
|       └───── main.css
└──── spec
    ├──── application_controller_spec.rb
    └──── spec_helper.rb
```

So I set up the below if you want to just copy and paste into a terminal:
First ``mkdir app_name`` then ``cd app_name `` 

```
touch config.ru
bundle init Gemfile
touch Rakefile
touch README

mkdir app
mkdir app/models 
mkdir app/views 
  touch app/views/index.erb
  touch app/views/layout.erb

mkdir app/controllers
  touch app/controllers/application_controller.rb

mkdir config  
 touch config/environment.rb 

mkdir db
 mkdir db/migrate
 touch db/seeds.rb
     
mkdir public   
 mkdir public/images
 mkdir public/javascript
 mkdir public/stylesheets
   touch public/stylesheets/main.css
```      

I found it easier to copy and paste the above information to get the files I need in my application going. 

After getting my file structure set up it is important to add all the gems you may require

<a href="http://sinatrarb.com/intro.html"> Sinatra</a> ``bundle add sinatra``

<a href="https://github.com/sinatra-activerecord/sinatra-activerecord"> Sinatra-activerecord </a> ``bundle add sinatra-activerecord``

<a href="https://rubygems.org/gems/activerecord/versions/5.0.0.1"> activerecord </a> ``bundle add activerecord``

<a href="https://www.sqlite.org/index.html"> sqlite3 </a> ``bundle add sqlite3``

<a href="https://github.com/pry/pry"> pry </a> ``bundle add pry``

<a href="https://github.com/jarmo/require_all"> require_all </a>  ``bundle add require_all``

<a href="https://github.com/rtomayko/shotgun"> shotgun </a> ``bundle add shotgun``

then you must run ``bundle install`` 


Feel free to add as many gems that you may require to proceed with your project. After completing that you need to make sure that your files are connected correctly and have the correct information inside of them. I cover that in a future post. 



