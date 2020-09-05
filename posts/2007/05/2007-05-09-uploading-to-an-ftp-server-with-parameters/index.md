---
title: "Uploading to an FTP server with parameters"
date: "2007-05-09"
---

This post will have a limited audience (even more limited than my normal posts!), but if you're searching for a solution to this particular problem, I hope you'll be glad you found this.

I was recently tasked with uploading a file to an FTP server. I [optimistically estimated](http://www.hanselman.com/blog/SoftwareEstimationRememberThatTargetsAreNotEstimates.aspx) that it shouldn't take long as we're using .NET 2.0 and there's FTP stuff in 2.0.

But, the particular server I had to write to took parameters on the PUT command (something I'd never seen before). The put looked something like this:  
_PUT thefile.txt %destinationFilename.txt%param2%%param4_

The parameters tell the server things like what 'mailbox' to use, what account to use to write the file, etc. etc.

A quick bit of info on FTP:  you first send the **PUT** _request_, and get a _response_, followed by other _requests_ (for things like credentials), followed ultimately by sending a **STOR** _command_.

The .NET 2.0 implementation of FtpWebRequest does not take into account differences between the _'request_ (PUT)' parameters and the '_command_ (STOR) parameters'.

To get around this, one must use sockets directly.  I found a [Microsoft KB article](http://support.microsoft.com/kb/812409) that contained just that.  The sample demonstrated using pluggable protocol handlers.  I removed the bits that weren't relevant and modified it to handle _command_ parameters.

I fronted all this with an **FtpTransfer** class that deals with just uploading files. Typical usage looks like this:

FtpTransfer ftpTransfer \= new FtpTransfer( new Uri( @"ftp://serverRequiringParameters" ), @"yourUsername", @"yourPassword" );

ftpTransfer.UploadFileWithParameters( @"c:tempftptest.txt", @"destinationFilename.txt", @"%destinationFilename.txt%PARAM2%PARAM3" );

The source (and a Visual Studio 2005 project) can be download [here](http://dunnhq.com/SimpleFtpWithParameterisedPut.zip).
