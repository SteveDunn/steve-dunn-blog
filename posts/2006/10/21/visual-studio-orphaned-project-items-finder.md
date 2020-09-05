---
title: 'Visual Studio Orphaned Project Items Finder'
date: '2006-10-21T22:32:00+00:00'
status: publish
permalink: /index.php/2006/10/21/visual-studio-orphaned-project-items-finder
author: stevedunn
excerpt: ''
type: post
id: 89
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/visual-studio-orphaned-project-items.html
blogger_internal:
    - /feeds/32841709/posts/default/3303971775142593148
dsq_thread_id:
    - '6392273951'
---
The name is a bit of a mouthful, but sums up what it’s all about. It finds orphaned items in a Visual Studio project. Inspired by [Clean Source Plus](http://www.codinghorror.com/blog/archives/000368.html), this utility is a stand-alone application and also a right-click Explorer menu item.

Recently I came across several dozen projects that had been worked on by dozens of people for several years. Inevitably, there were files present in the source tree that were not part of the project.

This is a tool to find those files. Please feel free to download it from [CodePlex](http://www.codeplex.com/Wiki/View.aspx?ProjectName=VSOrphan). There is an [installer file](http://www.codeplex.com/Project/FileDownload.aspx?ProjectName=VSOrphan&DownloadId=3350) and the [source code](http://www.codeplex.com/Project/FileDownload.aspx?ProjectName=VSOrphan&DownloadId=3351) is also available. If you’d like to contribute to the project, please let me know.

To use it is very simple. Download it and run it, or right click a Visual Studio project in Explorer and ‘Find Orphaned Items…’.

Warning!
--------

I’ve tested this project on Visual Studio 2003 and 2005 projects. **I haven’t tested this on Web Projects or Web Application Projects (in Visual Studio 2005)**. I would recommend verifying what the application thinks are orhpaned items. If it continually gets it right, you can trust it more and check it less. If it continually gets it wrong, then please let me know!

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>