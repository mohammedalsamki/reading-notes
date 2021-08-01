# Summary IMAGES
* The <img> element is used to add images to a 
web page.
* You must always specify a src attribute to indicate the 
source of an image and an alt attribute to describe the 
content of an image.
* You should save images at the size you will be using 
them on the web page and in the appropriate format.
* Photographs are best saved as JPEGs; illustrations or 
logos that use flat colors are better saved as GIFs

Domain Modeling
Domain modeling is the process of creating a conceptual model in code for a specific problem. A model describes the various entities, their attributes and behaviors, as well as the constraints that govern the problem domain. An entity that stores data in properties and encapsulates behaviors in methods is commonly referred to as an object-oriented model.

A domain model that's articulated well can verify and validate the understanding of a specific problem among various stakeholders. As a communication tool, it defines a vocabulary that can be used within and between both technical and business teams.

Model epic fails videos
Imagine you've been tasked to build a program that models the popularity of epic fail videos. After months of painstaking research, you've determined that the two essential metrics for gauging popularity are an epic rating and whether or not the video has animals.

Since you'll be modeling the popularity of many types of videos—parkour epic fails, corgi epic fails, etc.—you'll want to build self-contained objects with the same attributes and behaviors. That way, when you need to change the algorithm for determining popularity, the changes will be small and targeted.



As you read this article, type out and run all code samples you come across. Do not copy and paste. Writing out and testing your code will help you remember how to implement domain models in JavaScript later.

Define a constructor and initialize properties
To define the same properties between many objects, you'll want to use a constructor function. Below is a table that summarizes a JavaScript representation of an EpicFailVideo object.

Property	Data	Type
epicRating	1 to 10	Number
hasAnimals	true or false	Boolean
Here's an implementation of the EpicFailVideo constructor function.
