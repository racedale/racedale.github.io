---
layout: post
title: "Added to the website"
date: 2014-01-16 08:31:21 -0600
comments: true
categories: 
---
I spent another 4 hours adding to the website and tweaking things.  I added google analytics to the site to track when people visit and what they click on.  I changed the logo for github so that it doesn't look like the Google 'g', later I'll change the googleplus logo because right now it is a Picasa logo.  Changed the stupid default font for my name and replaced it with Google's Roboto webkit font family.  The search function still doesn't seem to work for me but that's not a crucial difference right now. I added some rake tasks to the rake file that will rename the filenames in the _posts directory so that the filenames will match the post dates (for anytime that the post is created, and worked on for long enough that the post time is different from when it's created.  Because the name of the file is the url).  Another rake task that pings Google, Bing, and Pingomatic about new changes to the website.  I've contemplated adding a rake task that will make posts unpublished by default, but if I did that I'll have to find a way to delete files from Amazon s3 or else there would be duplicates.  
Now my method of deploying is:  
    rake generate   
    git add .   
    git commit -m 'some comment about the post'  
    git push origin source   
    rake deploy   
    rake s3   
    rake notify   