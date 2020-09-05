---
title: 'Adding folders to the Class View in Visual Studio'
date: '2008-11-19T12:16:00+00:00'
status: publish
permalink: /index.php/2008/11/19/adding-folders-to-the-class-view-in-visual-studio
author: stevedunn
excerpt: ''
type: post
id: 58
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2008/11/adding-folders-to-class-view-in-visual.html
blogger_internal:
    - /feeds/32841709/posts/default/7023009540502928871
dsq_thread_id:
    - '8090402383'
---
I didn’t know this, but you can add folders to the Class View. You can then drag classes to it. What’s even better, you can drag <span style="font-weight: bold">methods</span> to it!

Thanks to Sara Ford for her [post](http://blogs.msdn.com/saraford/archive/2008/10/31/did-you-know-you-can-create-folders-to-organize-your-objects-and-methods-within-the-class-view-347.aspx) describing this.

There’s more good news! When you’re editing code in the editor and you’re over a class or method, you can use the ‘Synchronise Class View’ command (I’ve mapped mine to a keyboard short-cut, but you can add a[ toolbar item](http://www.danielmoth.com/Blog/2005/05/synchronize-class-view.html)) to synchronise the Class View to the item you’re currently editing. Once synchronised, you can go to Class View and drag that into one of your folders. Also, when you do this, you won’t upset any of your team with changes to the solution or project files – because these are <span style="font-weight: bold">your</span> settings, and hence are stored in the .suo file <span style="font-style: italic">(which, on the other hand could be a pain, because user option files shouldn’t be checked into your source repository)</span>.

Anyway, this is the next best thing to a ‘bread-crumb’ feature in the editor that let’s you jump around to favourite places in the the code. Maybe the bread-crumb feature will be in the next version of ReSharper?

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>