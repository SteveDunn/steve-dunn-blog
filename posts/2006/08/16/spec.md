---
title: 'Spec#'
date: '2006-08-16T20:07:00+00:00'
status: publish
permalink: /index.php/2006/08/16/spec
author: stevedunn
excerpt: ''
type: post
id: 106
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/08/spec.html
blogger_internal:
    - /feeds/32841709/posts/default/115575524640482865
---
Spec# is an addition to C# to allow specifications to be explicitly added to methods. Specifications can state that a method takes a string (which must be non-nul), an integer (which must be between 0 and n), or an array (of which all entries must be non null). Previously in C#, this would have meant a fair few lines of code that manually checked parameters and threw the respective exceptions. Furthermore, without specifications, you cannot force any over-ridden method to comply to the same specification.

Spec# is currently a research project and can be downloaded at <http://research.microsoft.com/specsharp/>

It can be installed to run in Visual Studio 2003 and 2005. For both systems, it requires an application called Simplify. This is a java application that can be downloaded at HP Labs Java Programming Toolkit page. The zipped file that contains Simplify.exe can be found at <http://www.hpl.hp.com/downloads/crl/jtk/download-escjava.html>, but don’t forget to first read the licence at <http://www.hpl.hp.com/downloads/crl/jtk/agreement.html> 😉

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>