---
title: 'A fast way of converting C# enums to strings–and back again.'
date: '2011-08-17T22:45:00+00:00'
status: publish
permalink: /index.php/2011/08/17/a-fast-way-of-converting-c-enums-to-strings-and-back-again
author: stevedunn
excerpt: ''
type: post
id: 32
category:
    - 'c#'
    - open-source
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2011/08/fast-way-of-converting-c-enums-to.html
blogger_internal:
    - /feeds/32841709/posts/default/2313438609525475397
dsq_thread_id:
    - '5987273061'
---
I recently needed a fast way of converting lots of enums to strings (and back again). I needed to do it very quickly. ‘Enum.Parse’ just wasn’t fast enough.

I discovered there was no ‘enum mapper’ in C#, so I knocked up [this little class](https://gist.github.com/1152680). It uses reflection just once when it comes across a new enum.

It’s compatible with .NET 3.5 too.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>