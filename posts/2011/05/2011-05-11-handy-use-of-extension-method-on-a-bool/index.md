---
title: "Handy use of extension method on a bool"
date: "2011-05-11"
---

I don’t like to overuse if/else statements.  I really dislike seeing code like this:

https://gist.github.com/SteveDunn/2bd239bdcdd517efc845022b6ded45e5

I just had an idea about using extension methods so I can write this instead:

https://gist.github.com/SteveDunn/c68d85b681c94ebd2b501bf3e247cb2c

and here’s the extension method:

https://gist.github.com/SteveDunn/c7180f57adb98a946dd70e5de9cef5c8

Nice or not? I think it reads a bit better (for single line expressions anyway).
