---
title: FluentInterface
date: '2007-01-17T14:03:00+00:00'
status: publish
permalink: /index.php/2007/01/17/fluentinterface
author: stevedunn
excerpt: ''
type: post
id: 79
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2007/01/ive-posted-before-about-stringbuilder.html
blogger_internal:
    - /feeds/32841709/posts/default/4981670039336400735
dsq_thread_id:
    - '7711956812'
---
I’ve [posted before](http://stevedunns.blogspot.com/2006/08/quicky-stringbuilder-tip.html) about the StringBuilder tip in .NET.

Martin Fowler describes this as an [ExpressionBuilder ](http://www.martinfowler.com/bliki/ExpressionBuilder.html)pattern.

More formal terms are described in his post, for instance, a [FluentInterface](http://www.martinfowler.com/bliki/FluentInterface.html) which allows code like this:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
customer.newOrder() 
	.with(6, "TAL") 
	.with(5, "HPK").skippable() 
	.with(3, "LGV").priorityRush();
```

</div> I personally like this style but agree that if every object had these strange looking methods it would certainly pollute an API.

Another formal term describing how not to pollute an API is [CommandQuerySeparation](http://www.martinfowler.com/bliki/CommandQuerySeparation.html). Basically, this means that a method that changes the observable state of an object shouldn’t have a return value.

The ExpressionBuilder pattern is the solution to this: it is a seperate object that defines the FluentInterface and yet doesn’t pollute the API.

I’m glad that I now know more than 3 patterns, the [Factory pattern](http://en.wikipedia.org/wiki/Factory_pattern), the [Visitor pattern](http://en.wikipedia.org/wiki/Visitor_pattern), and the [Submarine pattern](http://dunnhq.com/SubmarinePattern).

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>