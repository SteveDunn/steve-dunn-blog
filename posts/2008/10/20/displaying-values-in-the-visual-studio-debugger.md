---
title: 'Displaying values in the Visual Studio Debugger'
date: '2008-10-20T13:51:00+00:00'
status: publish
permalink: /index.php/2008/10/20/displaying-values-in-the-visual-studio-debugger
author: stevedunn
excerpt: ''
type: post
id: 59
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2008/10/displaying-values-in-visual-studio.html
blogger_internal:
    - /feeds/32841709/posts/default/7682041183591784780
dsq_thread_id:
    - '6376326759'
---
Normally, when you display values in the Visual Studio debugger, you get formatting (quotes, tabs etc.) included. For instance, if you’ve got <span style="font-style: italic">string s = "Hello\[tab\]World";</span> then hovering over s in the debugger displays "HellotWorld". If you wanted to copy a value value to the clipboard (maybe because you landed on an exception and you want to send the error to <strike>the idiot that caused it</strike> your fellow colleague), you’d probably right click on the value and select ‘copy value’. This copies the value to the clipboard. Another way is to use the <span style="font-weight: bold">immediate window</span>. Using the example above, typing ‘s’ in the immediate window would produce:

 [![](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBkOfTnhI/AAAAAAAAARs/ycCmtOKDvtQ/s400/hw1.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBkOfTnhI/AAAAAAAAARs/ycCmtOKDvtQ/s1600-h/hw1.png)

 To get rid of formatting (the quotes and the control characters), use the <span style="font-style: italic; font-weight: bold">,nq</span> option:

 [![](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBjzDc4dI/AAAAAAAAARk/QemrhnrSNIU/s400/hw2.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBjzDc4dI/AAAAAAAAARk/QemrhnrSNIU/s1600-h/hw2.png)

This is useful in itself, but it really becomes invaluable if you want to show some XML. With the magical <span style="font-style: italic; font-weight: bold">,nq</span> switch, the following code: [![](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyDNmmpDSI/AAAAAAAAAR0/Bbide7cMp8E/s400/x1.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyDNmmpDSI/AAAAAAAAAR0/Bbide7cMp8E/s1600-h/x1.png)

produces the following output in the immediate window: [![](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyExCPdxHI/AAAAAAAAASM/Hk0LOH8w1yE/s400/x2.png)](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyExCPdxHI/AAAAAAAAASM/Hk0LOH8w1yE/s1600-h/x2.png)

Pretty useless, but if you add <span style="font-style: italic; font-weight: bold">,nq</span>, you get: [![](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyDvZxIR8I/AAAAAAAAASE/A_QbIwxvBmg/s400/x3.png)](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyDvZxIR8I/AAAAAAAAASE/A_QbIwxvBmg/s1600-h/x3.png)

Much nicer.

<span style="font-style: italic; font-weight: bold">nq</span> stands for <span style="font-style: italic; font-weight: bold">nice’n quick, </span>because it doesn’t waste time writing quotes.

Probably.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>