---
title: 'Retrieve your Windows OS Product Keys'
date: '2006-10-22T09:50:00+00:00'
status: publish
permalink: /index.php/2006/10/22/retrieve-your-windows-os-product-keys
author: stevedunn
excerpt: ''
type: post
id: 88
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/retrieving-windows-product-keys.html
blogger_internal:
    - /feeds/32841709/posts/default/5481022870983252552
---
Today I needed to get the Windows XP Product Key but didn’t have the neccessary information to hand. I did a search and found the [MagicJellyBean](http://www.magicaljellybean.com/) utility.

This worked but I was curious how it worked. I read around a little bit and discovered a snippet of [C# code](http://geekswithblogs.net/willemf/archive/2006/04/23/76125.aspx) from [Willem’s blog](http://geekswithblogs.net/willemf/).

I then modified it a bit and created my own C# WinForm application.

[![](http://2.bp.blogspot.com/_bIhihWOyLpw/RkX7c_97lUI/AAAAAAAAAAU/g_hQBEnxBsI/s400/prodkey2.jpg)](http://2.bp.blogspot.com/_bIhihWOyLpw/RkX7c_97lUI/AAAAAAAAAAU/g_hQBEnxBsI/s1600-h/prodkey2.jpg)

The application lists the most common product keys (Windows XP and Office) and has a button to search for more keys that look like product ID’s. It searches all keys in HKEY\_LOCAL\_MACHINE.

Here’s the [source code](http://files.dunnhq.com/KeyFinderSource.zip) and here’s the [binary](http://files.dunnhq.com/KeyFinder.exe). Note, the application depends on the .NET Framework 2.0. Also, save the binary before running it otherwise it’ll run with restricted permissions and won’t be able to probe the registry.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>