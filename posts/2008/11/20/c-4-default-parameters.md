---
title: 'C# 4 &#8211; Default Parameters'
date: '2008-11-20T13:04:00+00:00'
status: publish
permalink: /index.php/2008/11/20/c-4-default-parameters
author: stevedunn
excerpt: ''
type: post
id: 57
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2008/11/c-4-default-parameters.html
blogger_internal:
    - /feeds/32841709/posts/default/6674564964859119900
dsq_thread_id:
    - '7889947217'
---
Coming from a C++ background, I’m really pleased that there’ll eventually be [default parameters ](http://codebetter.com/blogs/matthew.podwysocki/archive/2008/10/29/c-4-0-named-and-optional-parameters-behind-the-scenes.aspx)built into the next version of C#. But I do think that C++ had a much cleaner way of handling them: it would only allow defaults from right to left, for instance:

```
void foo(int a, int b, int c=3, int d=4)
```

It wouldn’t let you do:

```
void foo(int a=1, int b=2, int c, int d)
```

C# will, so for the example above, you’d end up with method calls that could look like:

```
foo( ,  , 3, 4)
```

One feature that I still really miss from C++ is <span style="font-weight: bold;">const</span>. This keyword could be applied to methods or parameters, so a method declared as:

```
void foo(int a, int b) const
{
}
```

would be guaranteed to not modify the state of the object (except for mutable members)

A method declared as:

```
void foo (const Person person)
{
}
```

would be guaranteed to not modify the person.

Maybe C# 5?

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>