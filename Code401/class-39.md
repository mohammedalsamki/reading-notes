
# NextJs

## Assets
Next.js can serve **static assets**, like images, under **the top-level** `public` directory.


Files inside `public` can be referenced from the root of the application .


## Metadata

Meta tags are snippets of text that describe a page's content; the meta tags don't appear on the page itself, but only in the page's source code. Meta tags are essentially little content descriptors that help tell search engines what a web page is about.

```html
<head>
  <meta name="description" content="An example of a meta description. These show up in search engine results.">
</head>

```
__Next.js__ has a built-in Head component for appending elements to the head section of a page.

First, you need to import the `next/head` component at the top of your Next.js page:

```jsx
import Head from "next/head"
```
Then, you can create a new `<Head>` component that looks like this:

```jsx
<Head>
  <meta name="description" content="Meta description content goes here." />
</Head>
```

## CSS
Next.js has built-in support for CSS and Sass which allows you to import .css and .scss files.

Using popular CSS libraries like Tailwind CSS is also supported.

## React Context 
[REF](https://www.freecodecamp.org/news/react-context-for-beginners/)
