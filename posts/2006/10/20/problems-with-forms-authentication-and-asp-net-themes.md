---
title: 'Problems with Forms Authentication and ASP.NET Themes'
date: '2006-10-20T19:58:00+00:00'
status: publish
permalink: /index.php/2006/10/20/problems-with-forms-authentication-and-asp-net-themes
author: stevedunn
excerpt: ''
type: post
id: 90
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/forms-authentication-and-stylesheet.html
blogger_internal:
    - /feeds/32841709/posts/default/7016856304778492200
dsq_thread_id:
    - '6352487577'
---
[](http://dunnhq.com/formsauth2.png)

It’s sometimes the strangest (and seemingly irrelevant) combinations of technology that give you the most problems. For a good few hours I’ve been wondering why my web site, which uses [Forms Authentication](http://msdn2.microsoft.com/en-us/library/ykzx33wh.aspx) and Themes, was not displaying any formatting or images.

It turns out that the URLs specified in the authentication section in web.config are used for ALL resources. So, in my case, the page was trying to load a .css file but ASP.NET was redirecting the request to default.aspx, which of course, is not a style-sheet and has a different MIME type. Here’s the section of my web.config file:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
<pre style="background-color:#FFFFFF;;overflow: auto;"><span style="color: #0000FF;"><</span><span style="color: #800000;">authentication </span><span style="color: #FF0000;">mode</span><span style="color: #0000FF;">="Forms"</span><span style="color: #0000FF;">></span><span style="color: #000000;">
      </span><span style="color: #0000FF;"><</span><span style="color: #800000;">forms  </span><span style="color: #FF0000;">loginUrl</span><span style="color: #0000FF;">="Default.aspx"</span><span style="color: #FF0000;">
        defaultUrl</span><span style="color: #0000FF;">="Default.aspx"</span><span style="color: #FF0000;">
        protection</span><span style="color: #0000FF;">="All"</span><span style="color: #FF0000;">
        timeout</span><span style="color: #0000FF;">="30"</span><span style="color: #FF0000;">
        path</span><span style="color: #0000FF;">="/"</span><span style="color: #FF0000;">
        requireSSL</span><span style="color: #0000FF;">="false"</span><span style="color: #FF0000;">
        slidingExpiration</span><span style="color: #0000FF;">="true"</span><span style="color: #FF0000;">
        cookieless</span><span style="color: #0000FF;">="UseDeviceProfile"</span><span style="color: #FF0000;">
        domain</span><span style="color: #0000FF;">=""</span><span style="color: #FF0000;">
        enableCrossAppRedirects</span><span style="color: #0000FF;">="false"</span><span style="color: #0000FF;">/></span><span style="color: #000000;">
    </span><span style="color: #0000FF;"></</span><span style="color: #800000;">authentication</span><span style="color: #0000FF;">></span>
```

</div>To fix this, I allow unauthenticated access to the resources, which was straight-forward. I added the following to the web.config file:

<div style="padding-bottom: 0px; margin: 0px; padding-left: 0px; padding-right: 0px; display: inline; float: none; padding-top: 0px">```
<pre style="background-color:#FFFFFF;;overflow: auto;"><span style="color: #000000;"> </span><span style="color: #0000FF;"><</span><span style="color: #800000;">location </span><span style="color: #FF0000;">path</span><span style="color: #0000FF;">="App_Themes"</span><span style="color: #0000FF;">></span><span style="color: #000000;">
    </span><span style="color: #0000FF;"><</span><span style="color: #800000;">system.web</span><span style="color: #0000FF;">></span><span style="color: #000000;">
      </span><span style="color: #0000FF;"><</span><span style="color: #800000;">authorization</span><span style="color: #0000FF;">></span><span style="color: #000000;">
        </span><span style="color: #0000FF;"><</span><span style="color: #800000;">allow </span><span style="color: #FF0000;">users</span><span style="color: #0000FF;">="*"</span><span style="color: #0000FF;">/></span><span style="color: #000000;">
      </span><span style="color: #0000FF;"></</span><span style="color: #800000;">authorization</span><span style="color: #0000FF;">></span><span style="color: #000000;">
    </span><span style="color: #0000FF;"></</span><span style="color: #800000;">system.web</span><span style="color: #0000FF;">></span><span style="color: #000000;">
  </span><span style="color: #0000FF;"></</span><span style="color: #800000;">location</span><span style="color: #0000FF;">></span><span style="color: #000000;">
</span>
```

</div>The tricky part in finding this was that the page’s HTML looked fine, there were no errors, and saving the resulting HTML to a file and viewing it produced the right results.

Firefox’s JavaScript Console proved incredibly helpful in finding the problem:

[![](http://2.bp.blogspot.com/_bIhihWOyLpw/RkX8P_97lVI/AAAAAAAAAAc/6DtARTWtex4/s400/formsauth2.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/RkX8P_97lVI/AAAAAAAAAAc/6DtARTWtex4/s1600-h/formsauth2.png)   
Once I saw this, it all fell into place!

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>