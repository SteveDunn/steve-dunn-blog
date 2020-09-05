---
title: "Visual Studio Orphaned Project Items Finder"
date: "2006-10-21"
---

The name is a bit of a mouthful, but sums up what it's all about.  It finds orphaned items in a Visual Studio project.  Inspired by [Clean Source Plus](http://www.codinghorror.com/blog/archives/000368.html), this utility is a stand-alone application and also a right-click Explorer menu item.

Recently I came across several dozen projects that had been worked on by dozens of people for several years.  Inevitably, there were files present in the source tree that were not part of the project.

This is a tool to find those files.  Please feel free to download it from [CodePlex](http://www.codeplex.com/Wiki/View.aspx?ProjectName=VSOrphan).  There is an [installer file](http://www.codeplex.com/Project/FileDownload.aspx?ProjectName=VSOrphan&DownloadId=3350) and the [source code](http://www.codeplex.com/Project/FileDownload.aspx?ProjectName=VSOrphan&DownloadId=3351) is also available. If you'd like to contribute to the project, please let me know.

To use it is very simple.  Download it and run it, or right click a Visual Studio project in Explorer and 'Find Orphaned Items...'.

## Warning!

I've tested this project on Visual Studio 2003 and 2005 projects.  **I haven't tested this on Web Projects or Web Application Projects (in Visual Studio 2005)**.  I would recommend verifying what the application thinks are orhpaned items.  If it continually gets it right, you can trust it more and check it less.  If it continually gets it wrong, then please let me know!