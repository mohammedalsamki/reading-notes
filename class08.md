# Summary LISTS, TABLES AND FORMS


X In addition to the CSS properties covered in other 
chapters which work with the contents of all elements, 
there are several others that are specifically used to 
control the appearance of lists, tables, and forms.
X List markers can be given different appearances 
using the list-style-type and list-style image 
properties.
X Table cells can have different borders and spacing in 
different browsers, but there are properties you can 
use to control them and make them more consistent. 
X Forms are easier to use if the form controls are 
vertically aligned using CSS.
X Forms benefit from styles that make them feel more 
interactive.

Containing Elements
If one block-level element sits inside another 
block-level element then the outer box is 
known as the containing or parent element.
It is common to group a number of elements together inside a <div>
(or other block-level) element. For example, you might group together 
all of the elements that form the header of a site (such as the logo and 
the main navigation). The <div> element that contains this group of 
elements is then referred to as the containing element.
A box may be nested inside 
several other block-level 
elements. The containing 
element is always the direct 
parent of that element.
The orange lines in this diagram represent <div> elements. The 
header (containing the logo and navigation) are in one <div> element, 
the main content of the page is in another, and the footer is in a third. 
The <body> element is the containing element for these three <div>
elements. The second <div> element is the containing element for two 
paragraphs of Latin text and images (represented by crossed squares)
