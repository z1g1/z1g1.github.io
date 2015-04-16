---
layout: post
title: "Create a Link Blog With Tumblr and IFTT"
date: 2015-04-15
image: tumblr.jpg
tags: Tumblr,Link Blog, IFTT
---


At a [New America Foundation conference](http://www.newamerica.org/new-america/cybersecurity-for-a-new-america/) 

Have you ever asked yourself, "Where can I find a link to that aritcle I read last week"?  One of the ways you can solve this problem is to create your very own link blog.  One of the first examples I saw of this concept came from [Dave Winer](http://scripting.com/).  His [link blog](http://radio3.io/users/davewiner/) is powered by a piece of softawre he wrote called [radio3](http://radio3.smallpict.com/2014/09/01/gettingStartedWithRadio3.html).  Originally this tool required a user to spin up their own virtual machine to run their own server.  It's current itteration is a hosted web application which alleviates this main issue with getting your own link blog up off the ground.  Radio3 is a great tool which allows you to save links using a bookmarklet, automatically push links to Facebook and Twitter and have an archive of every intersting story you have found.

The one feature that missing from the current version of radio3 is the ability to have an export of all of your saved links into a CSV file.  By using a text file [1](#1) as your storage you can edit it on almost any system, process it using your favorite programming language, or store it for latter in a version contorl system.  A feature I wanted to preserve was the ability to run without requiring a user to run their own server.  The final version of this setup needed to:
1. Allow for links to be shared via a bookmarklet
1. Provide durable storage of links
1. Export this archive to a text file 
1. Cross post links to Twitter and Facebook 
1. Run without requirng a VM or server 

Since I was not ready to launch my new startup running link blogs as a service, RLBaaS is the new buzzword of 2015, I had to look for exsting web services.  I turned to Tumblr for the first two points.  If you want to share links on the Internet Tumblr is defintatly one place to do that.  Plus they offer a "[Post to Tumblr Bookmarklet](https://www.tumblr.com/apps)".  This covers 2 of 5 points but since the 1st result of the Google search for [export Tumblr](https://www.google.com/search?q=export+tumblr) isn't a link to Tumblr's version of the [Google Data Liberation Front](http://en.wikipedia.org/wiki/Google_Data_Liberation_Front) I needed a way to plug into Tumblr to pull the links into a text file without using some glue code sitting on a server somewhere. 

When you want to connect two webservices the go to place to look is [If This Then That (IFTT)](https://ifttt.com/).  IFTT lists a number of "chanels", services it can interact with, and allows you string these together into "recepies".  Each recepie has a trigger (if this), and an action to take (then that), I created four recepies to power my link blog:

|    #   | If This                               | Then                                          |
|------------------------------------------------------------------------------------------------|
|    1  | If a new Link Post is made on Tumblr  | Append to a text file within Dropbox           |
|    2  | If a new Link Post is made on Tumblr  | Append to a spreadsheet within Google Drive    |
|    3  | If a new Link Post is made on Tumblr  | Post the link to Facebook                      |
|    4  | If a new Link Post is made on Tumblr  | Post the link to Twitter                       |





## Prerequistes ##
* [Tumblr Account](https://tumblr.com)
* [Dropbox Account](https://dropbox.com)
* [IFTT Account](https://ifttt.com) 
* [Facebook Account](https://facebook.com)
* [Twitter Account](https://twitter.com)
* [Google Account](https://google.com) (Optional 


## Step by Step ##