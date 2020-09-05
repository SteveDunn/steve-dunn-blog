---
title: 'Converting System.Drawing.Color to HTML color (and vice-versa)'
date: '2006-08-18T22:35:00+00:00'
status: publish
permalink: /index.php/2006/08/18/converting-system-drawing-color-to-html-color-and-vice-versa
author: stevedunn
excerpt: ''
type: post
id: 104
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/08/converting-systemdrawingcolor-to-html.html
blogger_internal:
    - /feeds/32841709/posts/default/115593693877402278
---
#####  

This is something I need very rarely. So rare in fact that in-between uses it is completely removed from my memory, leaving just the fact that I know I’ve searched for it before!

To convert a .NET Color object to an HTML RGB or named color, use

<div>```
<span>string</span> colorAsString = ColorTranslator.ToHtml( _backgroundColor ) ;
```

</div>and vice-versa

<div>```
Color c= ColorTranslator.FromHtml( <span>@"#RRGGBB"</span> ) ;
```

</div><div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>