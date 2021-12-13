
# REACT 2

*  [Conditional Rendering](#Conditional-Rendering)
*  [Lists & Keys](#Lists-&-Keys)
*  [Forms](#Forms)
*  [Lifting State](#Lifting-State)
*  [Composition vs Inheritance](#Composition-vs-Inheritance)
*  [Thinking in React](#Thinking-in-React)
# Conditional Rendering
In React, you can create distinct components that encapsulate behavior you need. Then, you can render only some of them, depending on the state of your application. Conditional rendering in React works the same way conditions work in JavaScript.

## Conditionally
-   If Component.
-   IIFE.
-   Variable.
-   Render Function.
-   Component.
-   Ternary.
-   The And Operator.
-   What if the Component Needs to Hide Itself?




# Lists & Keys
Keys help React distinguish items in a list. It helps React manage the changed items, new items added, or items removed from the list. We can output lists JavaScript arrays and the map() function.

key is used to identify unique elements, so that between 2 render passes React knows if an element is a new thing or an updated thing. Remember that React diffs each render to determine what actually changed in the DOM.

# Forms
    React-hook-form is a library that helps you validate forms in React. React-hook-form is a minimal library without any other dependencies. It is performant and straightforward to use, requiring developers to write fewer lines of code than other form libraries.


# Lifting State 
`sharing state`

moving it up to the closest common ancestor of the components that need it. This is called “lifting state up”. We will remove the local state from the TemperatureInput and move it into the Calculator instead.

# Composition vs Inheritance
development pattern based on React's original component model where we build components from other components using explicit defined props or the implicit children prop.

# Thinking in React