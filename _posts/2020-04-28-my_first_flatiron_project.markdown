---
layout: post
title:      "My First Flatiron Project"
date:       2020-04-28 10:51:34 -0400
permalink:  my_first_flatiron_project
---

Please find article here: https://medium.com/@sincerelybr/my-first-flatiron-project-94824e72e39b


---

It took me a while to even come up with a project idea and honestly I did not think of it on my own. I mean I seriously had no idea, I searched Digimon, Marvel, Goodreads, Yahoo weather(do not do it). I went to https://www.programmableweb.com/category/all/apis. Eventually I gave up and saw that an idea/example was given on the Learn.co directions. The example read:
"News reader - List articles and read an article of your choosing."
I thought to myself, perfect! Every one needs/wants to know whats going on in the world and I can find an api that can help me display the news to the user. I thought about what I wanted my application to do and how I wanted the user to interact with the application. I created a pseudo-code:
‌I want to give a user 3 options:
1. List the top articles of the day
2. Search for the top 3 articles based off a key word/description
3. Return to the home page
I searched the web and found an NewsAPI that sounded like it contained exactly what I needed to complete my goal. https://newsapi.org/
Perfect, GREAT! now what. . . .
Now I had to watch various videos on how to proceed with using an API to create my own application. Luckily I have an amazing cohort lead that met with us often and gave us various resources to guide us through this process.
I realized that I had to learn new things such as
How to create a GEM
How to push to Github from the command line
How to organize my files - CLI, Scraper file, and Api Manager
How to use and hide an API KEY
How to code HAHA!



---

CREATING A GEM/SETTING UP EVERYTHING:
First thing I had to do was make my application a GEM. I thought to myself, what does that mean. So I googled the bundle documentation: https://bundler.io/man/bundle-gem.1.html.
The gem allowed me to generate a directory named NewsApp with a Rakefile, GEM_NAME.gemspec, and other supporting files and directories that I used to develop my rubygem. From there, I continued to build my application by creating a files that I knew I needed such as my api_manager.rb, cli.rb, scraper.rb, and console (to run my cli/project).
Something I learned during this process is what a shebang is (#!/usr/bin/ruby) - "The opening line is called a shebang because of the first two characters #!. This line provides the shell with the absolute path to the Ruby interpreter.
The two issues I had when setting up my program/GEM was that my NewsApp.gemspec file did not allow me to run because I had to comment out most of the items that stated "TODO" and added a link to the spec.homepage. My other issue is that I was unable to run bin/NewApp originally and had to run $ Chmod 777 on the file which I discovered sets permissions so that, users/owners can read, can write and can execute.


---

PUSHING TO GITHUB/SAVING MY WORK:
One thing I know everyone dislikes is working hard on a project (or just learning how to set up a project) and then losing all your work because you did not save the file or the computer falls apart. Us, developers and programmers, are lucky enough to have github to save our lives. I learned how to set up my project so that I could push/save to github. I used the following article as well as guidance from my co-lead to learn
$ git init
$git status
$git add .
$git commit -m "<message>"
$git push origin master
Git and Github - must know commands to make your first commit
You want to learn github and how to contribute to the open source? You don't know how to use github with all its…dev.to


---

THE SET-UP: HOW MY FILES ARE SUPPOSED TO INTERACT
A major part of this project was ensuring that we understood OOP and the layout of our projects.
It took me a while to fully grasp the layout I was working on. At first I was just watching videos and following them to the best of my ability but then after playing around, I realized EXACTLY how my files needed to interact. My environment was in charge of holding all of my requires. It was in charge of making sure when someone runs "bundle install" the application will run because it is requiring all the GEMS and all the relative files needed to get the application going.
My bin/console is in charge of requiring my environment and running my CLI.
My CLI is in charge of obtaining information from the user and displaying that information to the user. The CLI the Command line interfaces are also called command-line user interfaces, console user interfaces and character user interfaces.
My API Manager is in charge of getting all of the information from my API URL endpoint, in this case newsapi.org and parsing through that information. (Parsing is the art of making sense of a bunch of strings and converting them into something we can understand.)
The api manager information is then send to my scraper file (usually through a method) in which I sort through that information and save it so that my CLI can refer to it and give it to the user. How I understand it, the scraper in short was in charge of representing the api manager information but also making the information "mine".
I learned a lot during this process including how to store my API key in a folder that can be ignored when you push to github, if you store the folder in your gitignore file.


---

HOW TO CODE - My hardest struggle
My biggest struggle PAGINATION! I struggled with pagination for a while. For some reason I could not get the idea on how to get my information to the next page. IN ADDITION, the newsApp did not allow developers or users to get more than 100 items at a time. I watched the video below and still sat there confused as HECK!
