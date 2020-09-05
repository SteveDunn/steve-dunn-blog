---
title: 'Programs that launch (or should launch) Visual Studio'
date: '2009-03-03T12:34:00+00:00'
status: publish
permalink: /index.php/2009/03/03/programs-that-launch-or-should-launch-visual-studio
author: stevedunn
excerpt: ''
type: post
id: 51
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2009/03/programs-that-launch-or-should-launch.html
blogger_internal:
    - /feeds/32841709/posts/default/3899971527459743981
---
Programs such as [FxCop](http://msdn.microsoft.com/en-us/library/bb429476(VS.80).aspx) provide links to source files that can be clicked and then edited in Visual Studio.

FxCop recently *(probably since I went 64bit, but also possibly a side-effect of running Windows 7)* started failing when clicking these links. It said:

> *Could not start Microsoft Visual Studio. Try specifying an alternate source code editor in Application Settings.*

Maybe it just looks in Program FilesMicrosoft Visual Studio\[whatever version\]. Anyway, I couldn’t see anything in the event log or any local FxCop logs, so I just changed the setting under ToolsSettings to use an explicit path to devenv.exe.

This worked, although it started a new instance of the IDE for every file. To get around that, you need to use the **/Edit** argument. Here’s what it looks like (click to make it bigger):

[![sshot-2](http://lh5.ggpht.com/_bIhihWOyLpw/Sa0VqI_zwYI/AAAAAAAABio/auvddtXA9Oo/sshot-2_thumb%5B4%5D.png?imgmax=800 "sshot-2")](http://lh6.ggpht.com/_bIhihWOyLpw/Sa0VpfS7CrI/AAAAAAAABik/JXo2ssdJd_g/s1600-h/sshot-2%5B6%5D.png)

> 

There’s other handy switches, some of which I knew about, like building a particular project/solution (to get the full list, run devenv.exe /?). It now uses an existing instance of Visual Studio if one’s present, otherwise it starts one up.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>