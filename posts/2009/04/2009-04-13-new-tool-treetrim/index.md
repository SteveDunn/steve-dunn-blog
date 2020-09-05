---
title: "New tool: TreeTrim"
date: "2009-04-13"
coverImage: "hammer-5B5-5D.png"
---

![hammer](images/hammer-5B5-5D.png "hammer") I've recently been working on a [tool](http://code.google.com/p/treetrim/) based on [Jeff Atwoods](http://www.codinghorror.com/blog/) [Clean Sources Plus](http://www.codinghorror.com/blog/archives/000368.html). 

It's called **TreeTrim**.  It's a tool that strips out debug files and folders in your source code tree and also zips and emails amongst other things.

One of the BIG requests for CleanSourcePlus (well, amongst the 5 people in the comments section of the tool's page!) is for the tool to make a working copy of your source before it deletes and zips.  TreeTrim does this.

It's plug-in based, so if it doesn't do something that you want, you can write your own plug-in, plonk it in the directory, and have the tool run it alongside the other plugins.

The installer and source code is available for download at [http://code.google.com/p/treetrim/](http://code.google.com/p/treetrim/)
