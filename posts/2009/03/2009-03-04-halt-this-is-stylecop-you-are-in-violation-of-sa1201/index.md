---
title: "Halt, this is StyleCop.  You are in violation of SA1201!"
date: "2009-03-04"
coverImage: "sshot-2_thumb-5B3-5D.png"
---

[StyleCop](http://code.msdn.microsoft.com/sourceanalysis) has a law rule named [SA1201](http://www.thewayithink.co.uk/stylecop/sa1201.htm). It says that you should put various parts of your code in the correct order.  For the contents of a class this goes like:

1. Fields
2. Constructors
3. Finalizers (Destructors)
4. Delegates
5. Events
6. Enums
7. Interfaces
8. Properties
9. Indexers
10. Methods
11. Structs
12. Classes

Doing all this by hand is tedious, but as with most things, [ReSharper](http://www.jetbrains.com/resharper/) (R#) makes it easier!

R# has a couple of features that, when combined, will mean you are fully SA1201 compliant (and, quite possibly well within the [20 seconds compliance window](http://www.entertonement.com/clips/39146/You-have-20-seconds-to-comply)!)  Firstly, there is a feature called Code Cleanup:

[![sshot-2](images/sshot-2_thumb-5B3-5D-300x248.png "sshot-2")](/wp-content/uploads/2009/03/sshot-2_thumb-5B3-5D.png)

You can get R# to do various things during code clean-up.  One of them is Reorder Type Members.  R# does a decent job of moving stuff around by default, but it’s not perfect and doesn’t stop all warnings about SA1201.  Thankfully, Reorder Type Members is configurable.  The interface is straight XML in the R# Options screen.  It’d be nice to have a GUI over it, but as yet (in R# 4.1 and [4.5](http://www.jetbrains.net/confluence/display/ReSharper/ReSharper+4.5+Nightly+Builds)), there isn’t one.  Thankfully, you can’t bugger things up too much as the XML is validated against an XSD before it’s saved.

I was going through a legacy project recently and wanted a way to automatically reorder things, so I modified the R# XML configuration.  To get your environment set-up, [download the new XML configuration](http://stevedunns.googlepages.com/ReSharperReorderTypeMembersConfigura.xml), go to ReSharper/Options and under languages/C# there an entry named **Type Members Layout**.

[![sshot-3](images/sshot-3_thumb-5B3-5D-300x206.png "sshot-3")](/wp-content/uploads/2009/03/sshot-3_thumb-5B3-5D.png)

Deselect _Use Default Patterns_ check-box and past in the new XML and click OK.

If you want a C# class that contains most of the things that should be reorganised, [download it here](http://stevedunns.googlepages.com/Class1.cs).  Mash it up a bit and then run StyleCop on it to ensure no SA1201 errors.