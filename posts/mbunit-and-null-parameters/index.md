---
title: "MbUnit and null parameters"
date: "2006-09-29"
---

I've recently moved from NUnit to MbUnit.  I like the extra features it offers, in particular, the RowTest feature.  This allows a single test to take different parameters - the parameters of which are specified in the attributes.  Here's an example:

class Test
{ internal Test( string s )
    { if( string.IsNullOrEmpty( s ) ) throw new ArgumentNullException( ) ;
    }
}

\[ RowTest \]
\[ Row( @"Hello World!" )\]
\[ Row( @"Another string" )\] public void Test1( string val )
{
    Test t \= new Test( val );
} 

Here, Test1 is being given the parameters from the attributes on the test.  Previously, say, in NUnit, I'd have written a couple of unit tests that create this Test object and give it different values.  Normally, I'd also write a couple that would try and create one with a null string and an empty string and assert that it throws an ArgumentNullException.

Now, in MbUnit, I went to write the test like so:

 \[ RowTest \]
        \[ Row( null , ExpectedException \= typeof( ArgumentNullException ) ) \]
        \[ Row( @"Hello World!" )\] public void Test1( string val )
        {
            Test t \= new Test( val );
        } 

Strangely, this caused an internal error in MbUnit.  Reading around, It looks like MbUnit is taking the first parameter of Row and treating it as an array rather than a single parameter.  The complete non-obvious way around this is to cast the null to a string:

 \[ RowTest \]
        \[ Row( (string)null , ExpectedException \= typeof( ArgumentNullException ) ) \]
        \[ Row( @"Hello World!" )\] public void Test1( string val )
        {
            Test t \= new Test( val );
        } 

This now works.  Which is nice!
