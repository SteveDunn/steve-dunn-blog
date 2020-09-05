---
title: 'ReSharper Live Templates for validating parameters of public C# methods.'
date: '2006-10-04T07:21:00+00:00'
status: publish
permalink: /index.php/2006/10/04/resharper-live-templates-for-validating-parameters-of-public-c-methods
author: stevedunn
excerpt: ''
type: post
id: 93
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/resharper-live-templates-for-validating.html
blogger_internal:
    - /feeds/32841709/posts/default/3052416656173580755
---
ReSharper Live Templates are smart shortcuts you can type and have filled in automatically. For instance, typing ‘foreach’ and pressing tab produces:

```
      foreach ( object o in something )
      {
      }
```

I’ve created 3 Live Templates for validating arguments in public methods (C#). Here’s a short [video demonstration](http://files.dunnhq.com/ReSharperLiveTemplateDemo.avi "Video demonstration of what I'm talking about"). I’ve [blogged about these before](http://stevedunns.blogspot.com/2006/08/reshaper-live-templates-for-validating.html) for ReSharper 1.5 and said that there’s no way to export/import the templates. But in ReSharper 2.0, there is! You can get them [here](http://files.dunnhq.com/ArgCheckLiveTemplatesForResharper.xml). Go to ReSharper/Options/Templates/LiveTemplates and click the ‘Import templates from file’ button.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>