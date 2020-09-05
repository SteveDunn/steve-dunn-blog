---
title: "A fast way of converting C# enums to strings–and back again."
date: "2011-08-17"
---

I recently needed a fast way of converting lots of enums to strings (and back again).  I needed to do it very quickly.  ‘Enum.Parse’ just wasn’t fast enough.

I discovered there was no ‘enum mapper’ in C#, so I knocked up [this little class](https://gist.github.com/1152680).  It uses reflection just once when it comes across a new enum.

It’s compatible with .NET 3.5 too.
