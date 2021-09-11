# What Is Node and When Should I Use It?
By James Hibbard
JavaScript
February 16, 2020
Share:

So you’ve heard of Node.js, but aren’t quite sure what it is or where it fits into your development workflow. Or maybe you’ve heard people singing Node’s praises and now you’re wondering if it’s something you need to learn. Perhaps you’re familiar with another back-end technology and want to find out what’s different about Node.

If that sounds like you, then keep reading. In this article, I’ll take a beginner-friendly, high-level look at Node.js and its main paradigms. I’ll examine Node’s main use cases, as well as the current state of the Node landscape, and offer you a wide range of jumping off points (for further reading) along the way.

Please note that, throughout the article, I’ll use “Node” and “Node.js” interchangeably.
What Is Node.js?

There are plenty of definitions to be found online. Let’s take a look at a couple of the more popular ones. This is what the project’s home page has to say:

    Node.js® is a JavaScript runtime built on Chrome’s V8 JavaScript engine.

And this is what Stack Overflow has to offer:

    Node.js is an event-based, non-blocking, asynchronous I/O runtime that uses Google’s V8 JavaScript engine and libuv library.

Hmmm, “event-based”, “non-blocking”, “asynchronous I/O” — that’s quite a lot to digest in one go. So let’s approach this from a different angle and begin by focusing on the other detail that both descriptions mention — the V8 JavaScript engine.
Node Is Built on Google Chrome’s V8 JavaScript Engine

The V8 engine is the open-source JavaScript engine that runs in Google Chrome and other Chromium-based web browsers, including Brave, Opera, and Vivaldi. It was designed with performance in mind and is responsible for compiling JavaScript directly to native machine code that your computer can execute.

However, when we say that Node is built on the V8 engine, we don’t mean that Node programs are executed in a browser. They aren’t. Rather, the creator of Node (Ryan Dahl) took the V8 engine and enhanced it with various features, such as a file system API, an HTTP library, and a number of operating system–related utility methods.

This means that Node.js is a program we can use to execute JavaScript on our computers. In other words, it’s a JavaScript runtime.
## How Do I Install Node.js?

In this next section, we’ll install Node and write a couple of simple programs. We’ll also look at npm, a package manager that comes bundled with Node.
