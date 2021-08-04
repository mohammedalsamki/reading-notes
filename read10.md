Top 10 Node.js Debugging Tips to Debug Like a Pro
LOU BICHARDOCTOBER 15, 2018DEVELOPER TIPS, TRICKS & RESOURCES



Err—not quite.

Whilst this tweet is painfully relatable, it also saddens me. This goes to show there are so many Node.js developers out there who are debugging their applications the caveman way. But debugging Node.js needn’t be this hard.

The more you relate to this tweet, the more you must read on. Your sanity begs you.

Today we’re going beyond just logging everywhere in your application. Many resources on Node.js debugging go through only one single method, but in this article, we’re going to cover ten unique tools you can use to debug your Node.js application like a pro.

Tip: Find application errors and performance problems instantly with Stackify Retrace
Troubleshooting and optimizing your code is easy with integrated errors, logs and code level performance insights.
Try today for free
Tip 1: Test
Testing shouldn’t be controversial. Yet spending the past few years as a consultant developer, I’ve now seen so many teams hand-wave at test-driven development and opt instead to put themselves into a world of pain. The tests you skip writing today will short-change your future developers’ debugging abilities.

Tests are so useful during debugging because you can use them as documentation of your code’s behavior and APIs. When you’re rifling through code searching for a bug and stop to ask yourself, “Hold up, why are they using a .forEach, not a .map?” it is immeasurably helpful to see the creator’s thoughts encapsulated in test case descriptions and example code.
