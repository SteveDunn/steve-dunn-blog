---
title: 'IDisposable alerts'
date: '2009-03-06T21:10:00+00:00'
status: publish
permalink: /index.php/2009/03/06/idisposable-alerts
author: stevedunn
excerpt: ''
type: post
id: 46
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2009/03/idisposable-alerts.html
blogger_internal:
    - /feeds/32841709/posts/default/5101870733589216424
dsq_thread_id:
    - '7112514885'
---
Types that implement IDisposable usually do so for a reason. They probably consume resources that should be released as early as possible.

In a recent project, I came across a very neat idea. In the destructor/finalizer/finaliser of your IDisposable type, do something to alert the consumer that you’re being collected by the Garbage Collector and hence you haven’t been disposed of correctly.

But how does this type know it’s not been disposed correctly? Well, if you follow the IDisposable pattern to the letter *(described in the excellent book Effective C# (Item 18), and about 3,000 places around t’internet)*, in your Dispose method, you’ll call GC.SupressFinalize(this); meaning the Garbage Collector won’t call your finalizer. So if you ever end up in the finalizer, the naughty user hasn’t called Dispose or hasn’t put the construction of your type in a using block.

There’s two bits to this

The constructor:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
public MyResourceHungryType( )
{
  _stackTrace = new StackTrace( ) ;
}
```

</div>The finalizer:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
~MyResourceHungryType( )
{
  Debug.WriteLine( _stackTrace.ToString( ) ) ;
}
```

</div>Then, if the finalizer is ever called, you’ll get a call stack printed up to the point where you created this type – something like:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
at Namespace.MyResourceHungryType..ctor()
   at Namespace.MyType.DoSomething()
   at SomeNamespace.SomeMethod()
```

</div>Handy.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>