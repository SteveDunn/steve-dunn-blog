---
title: "Adding folders to the Class View in Visual Studio"
date: "2008-11-19"
---

I didn't know this, but you can add folders to the Class View. You can then drag classes to it.   What's even better, you can drag methods to it!

Thanks to Sara Ford for her [post](http://blogs.msdn.com/saraford/archive/2008/10/31/did-you-know-you-can-create-folders-to-organize-your-objects-and-methods-within-the-class-view-347.aspx) describing this.

There's more good news! When you're editing code in the editor and you're over a class or method, you can use the 'Synchronise Class View' command (I've mapped mine to a keyboard short-cut, but you can add a [toolbar item](http://www.danielmoth.com/Blog/2005/05/synchronize-class-view.html)) to synchronise the Class View to the item you're currently editing.  Once synchronised, you can go to Class View and drag that into one of your folders.  Also, when you do this, you won't upset any of your team with changes to the solution or project files - because these are your settings, and hence are stored in the .suo file (which, on the other hand could be a pain, because user option files shouldn't be checked into your source repository).

Anyway, this is the next best thing to a 'bread-crumb' feature in the editor that let's you jump around to favourite places in the the code.   Maybe the bread-crumb feature will be in the next version of ReSharper?
