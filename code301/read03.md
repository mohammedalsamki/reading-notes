# Lists and Keys

First, let’s review how you transform lists in JavaScript.

Given the code below, we use the map() function to take an array of numbers and double their values. We assign the new array returned by map() to the variable doubled and log it:

const numbers = [1, 2, 3, 4, 5];
const doubled = numbers.map((number) => number * 2);console.log(doubled);

This code logs [2, 4, 6, 8, 10] to the console.

In React, transforming arrays into lists of elements is nearly identical.
Rendering Multiple Components

You can build collections of elements and include them in JSX using curly braces {}.

Below, we loop through the numbers array using the JavaScript map() function. We return a <li> element for each item. Finally, we assign the resulting array of elements to listItems:

const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>  <li>{number}</li>);

We include the entire listItems array inside a <ul> element, and render it to the DOM:

ReactDOM.render(
  <ul>{listItems}</ul>,  document.getElementById('root')
);

Try it on CodePen

This code displays a bullet list of numbers between 1 and 5.
Basic List Component

Usually you would render lists inside a component.

We can refactor the previous example into a component that accepts an array of numbers and outputs a list of elements.

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>    <li>{number}</li>  );  return (
    <ul>{listItems}</ul>  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,  document.getElementById('root')
);

When you run this code, you’ll be given a warning that a key should be provided for list items. A “key” is a special string attribute you need to include when creating lists of elements. We’ll discuss why it’s important in the next section.

Let’s assign a key to our list items inside numbers.map() and fix the missing key issue.

function NumberList(props) {
  const numbers = props.numbers;
  const listItems = numbers.map((number) =>
    <li key={number.toString()}>      {number}
    </li>
  );
  return (
    <ul>{listItems}</ul>
  );
}

const numbers = [1, 2, 3, 4, 5];
ReactDOM.render(
  <NumberList numbers={numbers} />,
  document.getElementById('root')
);
  
  ## Keys

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>    {number}
  </li>
);

The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:

const todoItems = todos.map((todo) =>
  <li key={todo.id}>    {todo.text}
  </li>
);

When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort:

const todoItems = todos.map((todo, index) =>
  // Only do this if items have no stable IDs  <li key={index}>    {todo.text}
  </li>
);
  
  Keys

Keys help React identify which items have changed, are added, or are removed. Keys should be given to the elements inside the array to give the elements a stable identity:

const numbers = [1, 2, 3, 4, 5];
const listItems = numbers.map((number) =>
  <li key={number.toString()}>    {number}
  </li>
);

The best way to pick a key is to use a string that uniquely identifies a list item among its siblings. Most often you would use IDs from your data as keys:

const todoItems = todos.map((todo) =>
  <li key={todo.id}>    {todo.text}
  </li>
);

When you don’t have stable IDs for rendered items, you may use the item index as a key as a last resort:

const todoItems = todos.map((todo, index) =>
  // Only do this if items have no stable IDs  <li key={index}>    {todo.text}
  </li>
);
