---
title: "Displaying values in the Visual Studio Debugger"
date: "2008-10-20"
---

Normally, when you display values in the Visual Studio debugger, you get formatting (quotes, tabs etc.) included. For instance, if you've got string s = "Hello\[tab\]World"; then hovering over s in the debugger displays "HellotWorld". If you wanted to copy a value value to the clipboard (maybe because you landed on an exception and you want to send the error to the idiot that caused it your fellow colleague), you'd probably right click on the value and select 'copy value'. This copies the value to the clipboard. Another way is to use the immediate window. Using the example above, typing 's' in the immediate window would produce:

 [![](images/hw1.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBkOfTnhI/AAAAAAAAARs/ycCmtOKDvtQ/s1600-h/hw1.png)

To get rid of formatting (the quotes and the control characters), use the ,nq option:

 [![](images/hw2.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyBjzDc4dI/AAAAAAAAARk/QemrhnrSNIU/s1600-h/hw2.png)

This is useful in itself, but it really becomes invaluable if you want to show some XML. With the magical ,nq switch, the following code: [![](images/x1.png)](http://2.bp.blogspot.com/_bIhihWOyLpw/SPyDNmmpDSI/AAAAAAAAAR0/Bbide7cMp8E/s1600-h/x1.png)

produces the following output in the immediate window: [![](images/x2.png)](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyExCPdxHI/AAAAAAAAASM/Hk0LOH8w1yE/s1600-h/x2.png)

Pretty useless, but if you add ,nq, you get: [![](images/x3.png)](http://4.bp.blogspot.com/_bIhihWOyLpw/SPyDvZxIR8I/AAAAAAAAASE/A_QbIwxvBmg/s1600-h/x3.png)

Much nicer.

nq stands for nice'n quick, because it doesn't waste time writing quotes.

Probably.
