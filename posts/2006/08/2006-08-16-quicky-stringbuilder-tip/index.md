---
title: "Quicky StringBuilder Tip"
date: "2006-08-16"
---

StringBuilder has an Append method that returns a reference to itself. This is useful for when you want to append several items in one go. The following code is an example. Obviously, you'll get more benefit the more items you add:

      StringBuilder sb = new StringBuilder( ) ;  
      string s = sb.Append( @"Hello " )  
        .Append( @"World" )  
        .ToString( ) ;

If you've been forced into programming in VB, then check out the original text of this tip at devx.com:

[http://www.devx.com/tips/Tip/28152](http://www.devx.com/tips/Tip/28152)
