# What is a Component?

A component is a modular, portable, replaceable, and reusable set of well-defined functionality that encapsulates its implementation and exporting it as a higher-level interface.

A component is a software object, intended to interact with other components, encapsulating certain functionality or a set of functionalities. It has an obviously defined interface and conforms to a recommended behavior common to all components within an architecture.

A software component can be defined as a unit of composition with a contractually specified interface and explicit context dependencies only. That is, a software component can be deployed independently and is subject to composition by third parties.

## Characteristics of Components

Reusability − Components are usually designed to be reused in different situations in different applications. However, some components may be designed for a specific task.

Replaceable − Components may be freely substituted with other similar components.

Not context specific − Components are designed to operate in different environments and contexts.

Extensible − A component can be extended from existing components to provide new behavior.

Encapsulated − A A component depicts the interfaces, which allow the caller to use its functionality, and do not expose details of the internal processes or any internal variables or state.

Independent − Components are designed to have minimal dependencies on other components.

## What is Props?

“Props” is a special keyword in React, which stands for properties and is being used for passing data from one component to another.
But the important part here is that data with props are being passed in a uni-directional flow. (one way from parent to child)
Furthermore, props data is read-only, which means that data coming from the parent should not be changed by child components.


1st Step: Defining Attribute & Data
We already know that we can assign attributes and values to HTML tags:
<a href="www.google.com">Click here to visit Google</a>;
Likewise, we can do the same for React components. We can define our own attributes & assign values with interpolation { }:
<ChildComponent someAttribute={value} anotherAttribute={value}/>
Here I’m declaring a “text” attribute to the ChildComponent and then assign a string value: “I’m the 1st child”.
<ChildComponent text={“I’m the 1st child”} />
Now the ChildComponent has a property and a value. Next, we need to pass it via Props.
2nd Step: Passing Data using Props
OK, now let’s take the “I’m the 1st child!” string and pass it by using props.
Passing props is very simple. Like we pass arguments to a function, we pass props into a React component and props bring all the necessary data.
Arguments passed to a function:
const addition = (firstNum, secondNum) => {  
  return firstNum + secondNum; 
};
Arguments passed to a React component:
const ChildComponent = (props) => {  
  return <p>I'm the 1st child!</p>; 
};
Props are arguments passed into React components. — w3schools.com
Final Step: Rendering Props Data
Alright so far, we have created an attribute and its value, then we passed it through props but we still can’t see it because we haven’t rendered it yet.
Prop is an Object
In the final step, we will render the props object by using string interpolation:
{props}
But first log props to console and see what it shows:
console.log(props);

As we can see, Props returns back an object. In JavaScript, we can access to object elements with dot(.) notation. So, let’s render our text property with interpolation:
const ChildComponent = (props) => {  
  return <p>{props.text}</p>; 
};