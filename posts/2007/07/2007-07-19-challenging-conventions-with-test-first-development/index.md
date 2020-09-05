---
title: "Challenging Conventions with Test First Development"
date: "2007-07-19"
---

I've just read a [great post](http://blog.objectmentor.com/articles/2007/07/17/testing-will-challenge-your-conventions) over at Tim Ottinger's blog.  In it he discusses how test first development challenges conventional development.  He makes several interesting points, some of which include:

> **Point 3: _Private makes less sense than it used to. You can’t test anything that’s private._**

This is something I often [ponder over](http://stevedunns.blogspot.com/2007/05/object-oriented-vs-test-oriented.html).  Making things private makes your _intent_ very clear, which I think is very important.  But private implementation is still a unit of code that needs testing.  Then again, as described in [Test Driven Development: A Practical Guide](http://www.amazon.co.uk/Test-Driven-Development-Practical-Guide/dp/0131016490),  unit tests should test the facets of _behavior._ As [Dave Astels](http://daveastels.com/) puts it in this [blog post](http://daveastels.com/2005/07/05/a-new-look-at-test-driven-development/):

_"... the idea of “unit” is a major problem. First of all it’s a vague term, and second it implies a structural division of the code (i.e. people think that they have to test methods or classes). We shouldn’t be thinking about units… we should be thinking about facets of behaviour."_

To me, the term 'facets of behaviour' reads that 'behaviour' has 'facets', and that private implementation makes up each facet.  So by testing the facets of behaviour, you are really testing units of private implementation (i.e. private methods).  This point may be worthy of a new post...

> **Point 4:  _The fat constructor argument list is a concession to the need for isolation and testing with mocks..._**

Good comment.  I always refactor any code I see with a fat parameter list so it takes a 'property bag' instead.  In ReSharper, this refactoring is called 'ExtractClassFromParameters'.  The benefit of this is cleaner, more separate code, and also overcomes C#'s limitation of not having default parameters (i.e. you leave it null/default in the property bag).

> **Point 7:  _Hard to use class interfaces are now hard for you to use..._**

Exactly.  Which is why I find TDD a great way to figure out 'how to design an API/Framework' rather than 'how to implement the API/Framework to achieve something'.  Something that made a lot of sense when reading the [Framework Design Guidelines](http://stevedunns.blogspot.com/2007/04/framework-design-guidelines-is.html) is to forget OO when designing the public interface to an API - i.e. design it so it's easy to use for the most common scenario.  Exactly what is achieved by practicing TDD.
