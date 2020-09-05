---
title: 'ThoughtWork’s Mingle on X64 machines'
date: '2009-02-26T11:20:00+00:00'
status: publish
permalink: /index.php/2009/02/26/thoughtworks-mingle-on-x64-machines
author: stevedunn
excerpt: ''
type: post
id: 52
category:
    - Uncategorised
tag: []
post_format: []
blogger_blog:
    - stevedunns.blogspot.com
blogger_author:
    - 'Steve Dunn'
blogger_permalink:
    - /2009/02/thoughtworks-mingle-on-x64-machines.html
blogger_internal:
    - /feeds/32841709/posts/default/6173033147875507883
---
By default, 32 bit applications installed on 64 bit machines are installed into the Program Files (x86) directory.

[Mingle](http://studios.thoughtworks.com/mingle-agile-project-management), in particular, Ruby doesn’t like the brackets in this path, hence, when Mingle tries to start, it fails. It writes the following entries to the log file in the program’s directory:

> Failed to load Rails: C:/Program Files (x86)/Mingle\_2\_2/app/controllers/caching/keys.rb:1: Invalid char `257’ (‘¯’) in expression C:/Program Files (x86)/Mingle\_2\_2/vendor/rails/activesupport/lib/active\_support/dependencies.rb:505:in `load’ C:/Program Files (x86)/Mingle\_2\_2/config/../vendor/rails/railties/lib/initializer.rb:475:in `load\_application\_initializers’ C:/Program Files (x86)/Mingle\_2\_2/config/../vendor/rails/railties/lib/initializer.rb:474:in `each’ C:/Program Files (x86)/Mingle\_2\_2/config/../vendor/rails/railties/lib/initializer.rb:474:in `load\_application\_initializers’ C:/Program Files (x86)/Mingle\_2\_2/config/../vendor/rails/railties/lib/initializer.rb:145:in `process’ C:/Program Files (x86)/Mingle\_2\_2/config/../vendor/rails/railties/lib/initializer.rb:93:in `run’ C:/Program Files (x86)/Mingle\_2\_2/config/environment.rb:116 C:/Program Files (x86)/Mingle\_2\_2/config/environment.rb:1

The solution: change the default installation to just Program Files. Handy. If you want to use Mingle. On a 64 bit machine.

<div class="sfsi_Sicons" style="width: 100%; display: inline-block; vertical-align: middle; text-align:left"><div style="margin:0px 8px 0px 0px; line-height: 24px"><span>Please follow and like us:</span></div><div class="sfsi_socialwpr"><div class="sf_subscrbe" style="text-align:left;float:left;width:64px">[![](/wp-content/plugins/ultimate-social-media-icons/images/follow_subscribe.png)](http://www.specificfeeds.com/widgets/emailSubscribeEncFeed/ZGtRQ2N4YUkxenJ6TjgzTy9FZTZGOVlUampBalh0Tk05THhhblhmbDRkb2xlM3YxSjJmQ2puZlhkODJzNmNaVzFMZUJvY3ovZkJzRldLdHVicHJwamNaaUZ5UXJqOFROOW5PV2pDMzBGZjNLSHo3aloyRTlJdkhJRDdWK0FNT3B8c3VkUm1QVE45WHJ3U0FIZVBnWG9lUUFXWWJvVDdIOXBsL2Q2NlduWE01dz0=/OA==/)</div><div class="sf_fb" style="text-align:left;width:98px"><div action="like" class="fb-like" data-layout="button" data-share="true" href="" send="false" showfaces="false" width="180"></div></div><div class="sf_twiter" style="text-align:left;float:left;width:auto">[](http://twitter.com/share)</div><div class="sf_pinit" style="text-align:left;float:left;line-height: 20px;width:47px">[](https://www.pinterest.com/pin/create/button/?url=&media=&description=)</div><div class="sf_google" style="text-align:left;float:left;max-width:62px;min-width:35px;"><div class="g-plusone" data-annotation="none" data-href="" data-size="large"></div></div></div></div>