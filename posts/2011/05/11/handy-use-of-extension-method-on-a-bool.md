---
title: 'Handy use of extension method on a bool'
date: '2011-05-11T20:41:00+00:00'
status: publish
permalink: /index.php/2011/05/11/handy-use-of-extension-method-on-a-bool
author: stevedunn
excerpt: ''
type: post
id: 33
category:
    - .net
    - 'c#'
    - tips
tag:
    - idea
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2011/05/handy-use-of-extension-method-on-bool.html
blogger_internal:
    - /feeds/32841709/posts/default/1035053383948661691
dsq_thread_id:
    - '6037834203'
---
I don’t like to overuse if/else statements. I really dislike seeing code like this:

<div class="oembed-gist"><script src="https://gist.github.com/SteveDunn/2bd239bdcdd517efc845022b6ded45e5.js"></script><noscript>View the code on [Gist](https://gist.github.com/SteveDunn/2bd239bdcdd517efc845022b6ded45e5).</noscript></div>I just had an idea about using extension methods so I can write this instead:

<div class="oembed-gist"><script src="https://gist.github.com/SteveDunn/c68d85b681c94ebd2b501bf3e247cb2c.js"></script><noscript>View the code on [Gist](https://gist.github.com/SteveDunn/c68d85b681c94ebd2b501bf3e247cb2c).</noscript></div>and here’s the extension method:

<div class="oembed-gist"><script src="https://gist.github.com/SteveDunn/c7180f57adb98a946dd70e5de9cef5c8.js"></script><noscript>View the code on [Gist](https://gist.github.com/SteveDunn/c7180f57adb98a946dd70e5de9cef5c8).</noscript></div>Nice or not? I think it reads a bit better (for single line expressions anyway).

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>