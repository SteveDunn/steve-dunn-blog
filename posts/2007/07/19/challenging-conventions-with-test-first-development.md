---
title: 'Challenging Conventions with Test First Development'
date: '2007-07-19T11:13:00+00:00'
status: publish
permalink: /index.php/2007/07/19/challenging-conventions-with-test-first-development
author: stevedunn
excerpt: ''
type: post
id: 65
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2007/07/challenging-conventions-with-test-first.html
blogger_internal:
    - /feeds/32841709/posts/default/4104996582307314106
dsq_thread_id:
    - '6382222383'
---
I’ve just read a [great post](http://blog.objectmentor.com/articles/2007/07/17/testing-will-challenge-your-conventions) over at Tim Ottinger’s blog. In it he discusses how test first development challenges conventional development. He makes several interesting points, some of which include:

> **Point 3: *Private makes less sense than it used to. You can’t test anything that’s private.***

This is something I often [ponder over](http://stevedunns.blogspot.com/2007/05/object-oriented-vs-test-oriented.html). Making things private makes your *intent* very clear, which I think is very important. But private implementation is still a unit of code that needs testing. Then again, as described in [Test Driven Development: A Practical Guide](http://www.amazon.co.uk/Test-Driven-Development-Practical-Guide/dp/0131016490), unit tests should test the facets of *behavior.* As [Dave Astels](http://daveastels.com/) puts it in this [blog post](http://daveastels.com/2005/07/05/a-new-look-at-test-driven-development/):

*“… the idea of “unit” is a major problem. First of all it’s a vague term, and second it implies a structural division of the code (i.e. people think that they have to test methods or classes). We shouldn’t be thinking about units… we should be thinking about facets of behaviour.”*

To me, the term ‘facets of behaviour’ reads that ‘behaviour’ has ‘facets’, and that private implementation makes up each facet. So by testing the facets of behaviour, you are really testing units of private implementation (i.e. private methods). This point may be worthy of a new post…

> **Point 4: *The fat constructor argument list is a concession to the need for isolation and testing with mocks…***

Good comment. I always refactor any code I see with a fat parameter list so it takes a ‘property bag’ instead. In ReSharper, this refactoring is called ‘ExtractClassFromParameters’. The benefit of this is cleaner, more separate code, and also overcomes C#’s limitation of not having default parameters (i.e. you leave it null/default in the property bag).

> **Point 7:  *Hard to use class interfaces are now hard for you to use…***

Exactly. Which is why I find TDD a great way to figure out ‘how to design an API/Framework’ rather than ‘how to implement the API/Framework to achieve something’. Something that made a lot of sense when reading the [Framework Design Guidelines](http://stevedunns.blogspot.com/2007/04/framework-design-guidelines-is.html) is to forget OO when designing the public interface to an API – i.e. design it so it’s easy to use for the most common scenario. Exactly what is achieved by practicing TDD.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>