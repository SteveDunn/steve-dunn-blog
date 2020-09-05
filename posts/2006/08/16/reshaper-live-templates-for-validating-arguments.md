---
title: 'Reshaper Live Templates for validating arguments'
date: '2006-08-16T20:15:00+00:00'
status: publish
permalink: /index.php/2006/08/16/reshaper-live-templates-for-validating-arguments
author: stevedunn
excerpt: ''
type: post
id: 105
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/08/reshaper-live-templates-for-validating.html
blogger_internal:
    - /feeds/32841709/posts/default/115575572596927769
dsq_thread_id:
    - '7567313955'
---
I strongly agree with the [‘contract](http://www.regdeveloper.co.uk/2005/12/29/first_among_equals/)‘ mataphor in API design, hence my interest in [Spec#](http://research.microsoft.com/specsharp/) (that I’ve [blogged about before](http://stevedunns.blogspot.com/2006/08/spec.html)).

To assist in this and to eliminate the tedium of writing argument checks, I’ve created 3 Resharper Live Templates. These check for

- null parameters for any object passed
- invalid parameters for any object passed
- null or empty check for any String passed.

These templates are called **‘arg’**, **‘argnull’** and **‘argempty’** respectivly.

Resharper 1.5 doesn’t allow importing or exporting of Live Templates from the GUI. They are however stored in an XML file at %userprofile%Application DataJetBrainsReSharperUserSettings.xml. Below is a chunk of XML that must be placed under the TemplateManagerTemplates node. If you have any others, please let me know!

> &lt;Template text=”if( $TYPE$$EXPRESSION$ )&amp;#xA; throw new ArgumentException( @&amp;quot;Cannot $ACTION$ as the value passed was invalid. Please provide a valid value.&amp;quot;, @&amp;quot;$TYPE$&amp;quot; ) ;&amp;#xA;” shortcut=”arg” description=”Throws an ArgumentException” kind=”livetemplate” reformat=”false” fileMask=”” context=”Everywhere” fileContext=”CSharp” enabled=”False” id=”1723695683″&gt;
> 
> &lt;Variables&gt;
> 
> &lt;Variable name=”TYPE” expression=”variableOfType(&amp;quot;System.Object&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;Variable name=”EXPRESSION” expression=”constant(&amp;quot; != 1&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;Variable name=”ACTION” expression=”constant(&amp;quot;PERFORM AN ACTION&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;/Variables&gt;
> 
> &lt;/Template&gt;
> 
> &lt;Template text=”if( $TYPE$ == null || $TYPE$.Length == 0 )&amp;#xA;throw new ArgumentNullException( @&amp;quot;$TYPE$&amp;quot;, @&amp;quot;Cannot $ACTION$ as the value passed was null or empty. Please provide a valid non null value.&amp;quot; ) ;&amp;#xA;” shortcut=”argempty” description=”Throws an ArgumentNullException when a string is null or empty” kind=”livetemplate” reformat=”true” fileMask=”” context=”Everywhere” fileContext=”CSharp” enabled=”False” id=”1705884294″&gt;
> 
> &lt;Variables&gt;
> 
> &lt;Variable name=”TYPE” expression=”variableOfType(&amp;quot;System.String&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;Variable name=”ACTION” expression=”constant(&amp;quot;PERFORM AN ACTION&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;/Variables&gt;
> 
> &lt;/Template&gt;
> 
> &lt;Template text=”if( $TYPE$ == null )&amp;#xA;throw new ArgumentNullException( @&amp;quot;$TYPE$&amp;quot;, @&amp;quot;Cannot $ACTION$ as the value passed was null. Please provide a valid non-null value.&amp;quot; ) ;&amp;#xA;” shortcut=”argnull” description=”Throws an ArgumentNullException” kind=”livetemplate” reformat=”true” fileMask=”” context=”Everywhere” fileContext=”CSharp” enabled=”False” id=”1497171628″&gt;
> 
> &lt;Variables&gt;
> 
> &lt;Variable name=”TYPE” expression=”variableOfType(&amp;quot;System.Object&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;Variable name=”ACTION” expression=”constant(&amp;quot;PERFORM AN ACTION&amp;quot;)” initialRange=”0″ /&gt;
> 
> &lt;/Variables&gt;
> 
> &lt;/Template&gt;

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>