---
title: 'Email certificate popups'
date: '2007-02-25T18:48:00+00:00'
status: publish
permalink: /index.php/2007/02/25/email-certificate-popups
author: stevedunn
excerpt: ''
type: post
id: 75
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2007/02/email-certificate-popups.html
blogger_internal:
    - /feeds/32841709/posts/default/3223891746282861535
dsq_thread_id:
    - '7859009340'
---
I recently switched to Vista and Office 2007. I set-up Outlook with the details of my email certificate. The trouble is, whenever sending a message, Vista pops up a dialog asking whether to grant or deny permission to the certificate. The exact text is:

> “Grant or Deny this application permission to use this key”.

The way around this is to not use Outlook to install the certificate but to right click on the certificate in Explorer and let Vista install it. Another important thing when doing this is to NOT click the Strong option – this is what causes the prompting – leave it as Medium.

To reinstall the certificate:

- Go to Internet Explorer/Tools/Option/Content/Certificates then Export your certificate (checking the box to delete it after export).
- Then, right click from Explorer and select Install.
- When this is done, reselect the certificate from Outlook – Tools/Trust Center/E\_mail Security.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>