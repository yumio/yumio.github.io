---
layout: post
title: "Trouble with Git"
date: 2016-07-23 11:57:55 -0400
categories: 
---

This may be common to many things, but one of the troubles that one can get into with using Git and Unix command line's up-arrow key "previous command line" feature is that you can get in the habit of running powerful commands from the CL without really knowing what you're doing.  The example is 

_git push -u origin master_ 

I was running this command as part of the trio of git add . and git commit after seeing it in codecademy's beginner tutorial.  It worked fine until it stopped working all of a sudden when I changed the user that was setup for my git commands.  Because of prior work I had done years ago on the computer for my first failed startup, the desktop Git was setup to push with another Git user account.  

So when I "fixed" this yesterday and started using my default account, all of a sudden the -u command seems to have stopped working and it was not pushing the correct branch to production.  

Now after doing the more advanced tutorial for Git, I now understand better what is going on, but for a while I was totally confused. 