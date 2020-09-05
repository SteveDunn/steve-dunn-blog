---
title: 'Visual Studio Build Tip'
date: '2006-10-18T08:18:00+00:00'
status: publish
permalink: /index.php/2006/10/18/visual-studio-build-tip
author: stevedunn
excerpt: ''
type: post
id: 92
category:
    - tips
    - 'visual studio'
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2006/10/visual-studio-build-tip.html
blogger_internal:
    - /feeds/32841709/posts/default/1348535320739378504
dsq_thread_id:
    - '5941367379'
---
By default, Visual Studio will build all of the projects in your solution regardless of any errors.

The problem with this is that if the first project it builds contains an error, the resulting binary will not get generated. If any other projects depend on this (which is normally the case, as it was the first to be built) then they’ll fail too, and so on to the end of the project heirarchy.

Pointless; you’ll spend ages sitting around in a locked IDE unable to edit the error until the build finishes.

You might as well stop at the first error. You could of press Ctrl+Break (several times) and hope that VS will eventually stop. But, there’s a better way: get Visual Studio to stop automatically after an error.

1. Go to Tools/Macros/Macro Explorer
2. Expand MyMacros
3. Double click Module1
4. This will bring up the macro in a new window. In that window, double click the EnvironmentEvents entry.
5. From the drop-down (currently ‘General’, select ‘Build Events’)
6. Select ‘OnBuildProjConfigDone’ and paste this in:

<span><span><span></span></span></span>

```
If Success = False Then 'The build failed...cancel any further builds.
DTE.ExecuteCommand("Build.Cancel")
End If<div><p>The whole method should look like this:</p>

Private Sub BuildEvents_OnBuildProjConfigDone( _  
ByVal Project As String, _ 
ByVal ProjectConfig As String, _ 
ByVal Platform As String, _ 
ByVal SolutionConfig As String, _ 
ByVal Success As Boolean) Handles BuildEvents.OnBuildProjConfigDone   
    If Success = False Then 'The build failed...cancel any further builds.     
        DTE.ExecuteCommand("Build.Cancel")   
    End If 
End Sub

</div>
<p></p>
<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px"><a href="http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/" target="_blank"><img src="/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png"></img></a></div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto"><a class="sr-twitter-button twitter-share-button" data-count="none" data-text="" data-url="" href="http://twitter.com/share" lang="en"></a></div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px"><a data-pin-count="none" data-pin-do="buttonPin" data-pin-save="true" href="https://www.pinterest.com/pin/create/button/?url=&media=&description="></a></div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>
```