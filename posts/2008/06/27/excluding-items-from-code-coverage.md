---
title: 'Excluding Items From Code Coverage'
date: '2008-06-27T20:20:00+00:00'
status: publish
permalink: /index.php/2008/06/27/excluding-items-from-code-coverage
author: stevedunn
excerpt: ''
type: post
id: 60
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2008/06/excluding-items-from-code-coverage.html
blogger_internal:
    - /feeds/32841709/posts/default/3919031299791654917
dsq_thread_id:
    - '6359433948'
---
<div><span style="font-family: "Arial","sans-serif"; font-size: 10pt">There’s an attribute in nCover that can be applied to your code to exclude it when doing code coverage. This is handy for auto-generated types such as web services etc. </span>

<span style="font-family: "Arial","sans-serif"; font-size: 10pt">The attribute is in the nCover assembly, but most people wouldn’t want to ship with their assemblies. Fortunately, you can define your own attribute. If you’re using TestDriven.NET, call it ‘CoverageExcludeAttribute’, if not, call it what you want.</span>

<span style="font-family: "Arial","sans-serif"; font-size: 10pt">When using NCover, pass the name of the attribute in the */ea WhateverYouCalledTheAttribute* command line attribute.</span>

<span style="font-family: "Arial","sans-serif"; font-size: 10pt">Here’s the code, with comments. Remember, don’t put this in a namespace!</span>

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
/// <summary> 
/// Use this attribute on types that do not need code coverage analysis. 
/// Such types are auto-generated types, such as web services etc. 
/// 
/// This attribute is used by TestDriven.NET to exclude the type/method in the 'test with coverage' functionality. 
/// This attribute can also be passed to NCover proper by using the /ea CoverageExcludeAttribute command line. 
/// </summary> 
/// <remarks> 
/// Note that this should NOT be part of a namespace! 
/// </remarks> 
[CoverageExclude] 
class CoverageExcludeAttribute : Attribute { } 
```

</div></div><div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>