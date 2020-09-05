---
title: 'Running unit tests in Visual Studio Express'
date: '2007-03-19T21:43:00+00:00'
status: publish
permalink: /index.php/2007/03/19/running-unit-tests-in-visual-studio-express
author: stevedunn
excerpt: ''
type: post
id: 74
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2007/03/running-unit-tests-in-visual-studio.html
blogger_internal:
    - /feeds/32841709/posts/default/194124793454938226
dsq_thread_id:
    - '6929723235'
---
The brilliant [TestDriven.net](http://testdriven.net/) can’t run in Visual Studio Express (well, from what I’ve heard, it **can**, but [Microsoft asked for it to be removed](http://weblogs.asp.net/nunitaddin/archive/2006/10/16/What-happened-to-TestDriven.NET-1.0_3F00_.aspx)).

Therefore, to run unit tests in Visual Studio Express, you must set your debugger application to point to NUnit.exe (or the brilliant [MBUnit](http://www.mbunit.com/)). This isn’t straightforward in Express and means editing the .csproj file by hand and telling it to run the NUnit exe.

Today, I wanted to run and debug some unit tests I’d written in the [XNA](http://msdn2.microsoft.com/en-us/xna/default.aspx) [Game Studio Express](http://msdn2.microsoft.com/en-us/xna/aa937795.aspx) (Visual Studio Express with some XNA bits bolted on). I couldn’t have the excellent right click/run unit test feature and I thought there’s got to be a better way than editing the .csproj file manually.

So I changed the unit test project to be a console application and added this to the Main method.

<div contenteditable="false" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">```
<pre style="overflow: auto; background-color: white"><div><span style="color: #000000">    </span><span style="color: #0000ff">public</span><span style="color: #000000"> </span><span style="color: #0000ff">static</span><span style="color: #000000"> </span><span style="color: #0000ff">void</span><span style="color: #000000"> Main( )<br></br>    {<br></br>      AppDomain.CurrentDomain.ExecuteAssembly( <br></br>        </span><span style="color: #000000">@"</span><span style="color: #000000">C:Program FilesNUnit-Net-2.0 2.2.9binNUnit-console.exe</span><span style="color: #000000">"</span><span style="color: #000000">,<br></br>        </span><span style="color: #0000ff">null</span><span style="color: #000000">,<br></br>        </span><span style="color: #0000ff">new</span><span style="color: #000000"> </span><span style="color: #0000ff">string</span><span style="color: #000000">[ ] { Assembly.GetExecutingAssembly( ).Location } );<br></br>    }<br></br></span></div>
```

</div>And it worked. Which was nice.

Update:
=======

Jamie recently left a message saying that the new Beta version DOES support Express editions! Read his post [here](http://weblogs.asp.net/nunitaddin/archive/2007/04/02/express-sku-support.aspx) and get [downloading](http://www.testdriven.net/download.aspx) straight away!

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>