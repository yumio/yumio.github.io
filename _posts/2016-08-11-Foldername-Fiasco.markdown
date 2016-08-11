---
layout: post
title: "Foldername Fiasco"
date: 2016-08-11 10:57:55 -0400
categories: 
---

What makes web development so hard for noobies is that there are so many _little_ things that you don't think matters, but to the computer, its a big deal.  Capitalization is one of these things.  

Most common operating systems in the last three decades have allowed file names and folder names to be equivalent, whether you used upper or lower case letters.  This probably eliminated a giant headache for customer support at Microsoft and Apple.  But in the world of Unix - "A" is NOT the same as "a" which allows for more precision and in some ways makes more sense they are technically different letters.

This, combined with the often cryptic way that systems throw error messages, can make web development frustratingly hard.  

Today (actually since yesterday) I've spent close to 5 hours trying to figure out why my Django setting that worked on my local server (my mac) didn't work on Heroku where I had uploaded my test site.  All it gave me repeatedly was "Template Does not Exist" error, although it clearly did.  

(Because of the troubleshooting, I did discover a useful trick "heroku run bash" which allows me to see the actual directory on the Heroku server - until today I had no idea how to do this)  

What was happening was that I had named my folder on my local server as "Templates" instead of "templates".  I quickly corrected this mistake on my local machine by going into Finder and renaming the folder there.  This seemed to have made it work on my local machine.  However, on github and also on Heroku, it turns out that renaming it on the local mac using Finder does not actually change the folder name.  Trying to overwrite the name using git does not recognize any changes.  The only way I was able to finally change the directory name was to rename it something else ("Templates" => template1" and then => "templates")  

Finally, this worked and its working on the Heroku server as well.  But man - that took a long time - and I guess these are the kinds of learnings you have as a developer, that you don't learn via courses or books.   

Lesson learned...