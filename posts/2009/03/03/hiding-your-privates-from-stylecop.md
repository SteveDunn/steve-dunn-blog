---
title: 'Hiding your privates from StyleCop'
date: '2009-03-03T12:55:00+00:00'
status: publish
permalink: /index.php/2009/03/03/hiding-your-privates-from-stylecop
author: stevedunn
excerpt: ''
type: post
id: 50
thumbnail: ../../../uploads/2009/03/sshot-1_thumb-5B2-5D.png
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2009/03/hiding-your-privates-from-stylecop.html
blogger_internal:
    - /feeds/32841709/posts/default/709299203569553598
dsq_thread_id:
    - '7847230167'
---
[I like StyleCop](http://dunnblog.azurewebsites.net/index.php/2009/02/21/stylecop/) but I didn’t like the fact it produced warnings on private fields and methods. I was wrong. Not wrong in that I didn’t like warnings on privates, but wrong that I thought there was no way to tell it to stop it.

Apparently there is. [Jason Allor](http://blogs.msdn.com/sourceanalysis/) kindly left a comment saying that it can be configured through the StyleCop settings dialog in Visual Studio.

I took a look and initially didn’t find it. I didn’t find it because I assumed there’d be different rules for public and private entities. But there’s not, you can decide at the *rule type* level:

[![sshot-1](http://lh3.ggpht.com/_bIhihWOyLpw/Sa0axMcd97I/AAAAAAAABiw/VsPPv7fowpo/sshot-1_thumb%5B2%5D.png?imgmax=800 "sshot-1")](http://lh6.ggpht.com/_bIhihWOyLpw/Sa0awff7anI/AAAAAAAABis/YyDDOL41w8c/s1600-h/sshot-1%5B4%5D.png)

It’d be nice to have separate rules for public and private. Currently, I’ve turned off **all** Documentation rules because I don’t like being warned that I haven’t commented private methods. However, I’d still like it to give me all the other great warnings if I do decide to comment a particular private method.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>