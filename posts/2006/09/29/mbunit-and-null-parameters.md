---
title: 'MbUnit and null parameters'
date: '2006-09-29T12:21:00+00:00'
status: publish
permalink: /index.php/2006/09/29/mbunit-and-null-parameters
author: stevedunn
excerpt: ''
type: post
id: 94
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/09/mbunit-and-null-parameters.html
blogger_internal:
    - /feeds/32841709/posts/default/115952886100266203
---
I’ve recently moved from NUnit to MbUnit. I like the extra features it offers, in particular, the RowTest feature. This allows a single test to take different parameters – the parameters of which are specified in the attributes. Here’s an example:

<div contenteditable="false" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">```
<pre style="background-color:White;"><div><span style="color: #0000FF; ">class</span><span style="color: #000000; "> Test
{
    </span><span style="color: #0000FF; ">internal</span><span style="color: #000000; "> Test( </span><span style="color: #0000FF; ">string</span><span style="color: #000000; "> s )
    {
        </span><span style="color: #0000FF; ">if</span><span style="color: #000000; ">( </span><span style="color: #0000FF; ">string</span><span style="color: #000000; ">.IsNullOrEmpty( s ) )
            </span><span style="color: #0000FF; ">throw</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">new</span><span style="color: #000000; "> ArgumentNullException( ) ;
    }
}

[ RowTest ]
[ Row( </span><span style="color: #000000; ">@"</span><span style="color: #000000; ">Hello World!</span><span style="color: #000000; ">"</span><span style="color: #000000; "> )]
[ Row( </span><span style="color: #000000; ">@"</span><span style="color: #000000; ">Another string</span><span style="color: #000000; ">"</span><span style="color: #000000; "> )]
</span><span style="color: #0000FF; ">public</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">void</span><span style="color: #000000; "> Test1( </span><span style="color: #0000FF; ">string</span><span style="color: #000000; "> val )
{
    Test t </span><span style="color: #000000; ">=</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">new</span><span style="color: #000000; "> Test( val );
}
</span></div>
```

</div>Here, Test1 is being given the parameters from the attributes on the test. Previously, say, in NUnit, I’d have written a couple of unit tests that create this Test object and give it different values. Normally, I’d also write a couple that would try and create one with a null string and an empty string and assert that it throws an ArgumentNullException.

Now, in MbUnit, I went to write the test like so:

<div contenteditable="false" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">```
<pre style="background-color:White;"><div><span style="color: #000000; ">        [ RowTest ]
        [ Row( </span><span style="color: #0000FF; ">null</span><span style="color: #000000; "> , ExpectedException </span><span style="color: #000000; ">=</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">typeof</span><span style="color: #000000; ">( ArgumentNullException ) ) ]
        [ Row( </span><span style="color: #000000; ">@"</span><span style="color: #000000; ">Hello World!</span><span style="color: #000000; ">"</span><span style="color: #000000; "> )]
        </span><span style="color: #0000FF; ">public</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">void</span><span style="color: #000000; "> Test1( </span><span style="color: #0000FF; ">string</span><span style="color: #000000; "> val )
        {
            Test t </span><span style="color: #000000; ">=</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">new</span><span style="color: #000000; "> Test( val );
        }
</span></div>
```

</div>Strangely, this caused an internal error in MbUnit. Reading around, It looks like MbUnit is taking the first parameter of Row and treating it as an array rather than a single parameter. The complete non-obvious way around this is to cast the null to a string:

<div contenteditable="false" style="padding-right: 0px; display: inline; padding-left: 0px; float: none; padding-bottom: 0px; margin: 0px; padding-top: 0px">```
<pre style="background-color:White;"><div><span style="color: #000000; ">        [ RowTest ]
        [ Row( (</span><span style="color: #0000FF; ">string</span><span style="color: #000000; ">)</span><span style="color: #0000FF; ">null</span><span style="color: #000000; "> , ExpectedException </span><span style="color: #000000; ">=</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">typeof</span><span style="color: #000000; ">( ArgumentNullException ) ) ]
        [ Row( </span><span style="color: #000000; ">@"</span><span style="color: #000000; ">Hello World!</span><span style="color: #000000; ">"</span><span style="color: #000000; "> )]
        </span><span style="color: #0000FF; ">public</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">void</span><span style="color: #000000; "> Test1( </span><span style="color: #0000FF; ">string</span><span style="color: #000000; "> val )
        {
            Test t </span><span style="color: #000000; ">=</span><span style="color: #000000; "> </span><span style="color: #0000FF; ">new</span><span style="color: #000000; "> Test( val );
        }
</span></div>
```

</div>This now works. Which is nice!

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>