---
title: 'BackgroundWorker &#8211; automating this handy class'
date: '2006-10-19T07:39:00+00:00'
status: publish
permalink: /index.php/2006/10/19/backgroundworker-automating-this-handy-class
author: stevedunn
excerpt: ''
type: post
id: 91
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/resharper-live-template-for-creating.html
blogger_internal:
    - /feeds/32841709/posts/default/8032375236534897037
---
[BackgroundWorker](http://msdn2.microsoft.com/en-us/library/system.componentmodel.backgroundworker.aspx) objects are an addition to .NET 2.0 to simplify asynchronous programming and are very useful in (but not restricted to) Windows Forms.

The basic idea is:

- Create a BackgroundWorker object
- Set-up various events on it, like DoWork, RunWorkerCompleted, and ProgressChanged
- Set-up various properties, like WorkerReportsProgress and WorkerSupportCancellation
- Call RunWorkerAysnc

…then, in your form you get notified of progress and can cancel the operation at any time.

I’ve created a [ReSharper](http://www.jetbrains.com/resharper/) Live Template that will help you create and set-up the BackgroundWorker object. You can download it [here](http://files.dunnhq.com/backgroundWorkerLiveTemplate.xml). For instructions on importing the Live Template into ReSharper, see my previous post [here](http://stevedunns.blogspot.com/2006/10/resharper-live-templates-for-validating.html).

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>