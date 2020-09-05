---
title: "Getting 'code://' hyperlinks into FlexWiki"
date: "2007-07-04"
---

[Reflector](http://www.aisto.com/roeder/dotnet/), when installed, adds a "_code://_" protocol handler, enabling hyperlinks to specified types in assemblies.  This handler is similar to http:// or ftp://, but instead of taking you to a web site, it takes you to a type in an assembly!

For example, _code://System.Web/System.Web.UI.WebControls.WebControl_ will launch Reflector and navigate to the WebControl type in the System.Web.UI.WebControls namespace.

Custom types can also be navigated to, although the associated assembly must be loaded first.

By default, FlexWiki does not handle all protocol handlers. To get it to handle the code:// protocol, a recompile is needed.  I'm working with version [2.0.0.41](http://builds.flexwiki.com/download/FlexWikiCore-20/2.0.0.41/). [Later versions](http://builds.flexwiki.com/download/FlexWikiCore-20/) are now available, but the code should be in a similar place.  So, for version 2.0.0.41, changes are needed to the file:  _FlexWikiCore-2.0.0.41-srcEngineSourceFormatter.cs_.

Change lines **1706** and **1707** \- adding the '**code|**' segment next to the _https?|_ text:

static string urlPattern \= @"((https?|code|ftp|gopher..." ) ; static string urlPatternInBrackets \= @"((https?|code|ftp|gopher..." ) ; 

I must say, it's very handy for your team to be able to navigate directly to code from a Wiki entry.
