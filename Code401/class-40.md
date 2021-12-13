# Class 40

# Next.js - Dynamic Routes

Next. js supports dynamic import() , which allows you to import JavaScript modules (including React components) dynamically and load each import as a separate chunk. ... In Next. js, these components are server-side rendered (SSR) by default.

## How Routing works in Next.js

Next.js uses the file system to enable routing in the app. Next automatically treats every file with the extensions `.js`, `.jsx`, `.ts`, or `.tsx` under the `pages` directory as a route.

A page in Next.js is a React component that has a route based on its file name.

Consider this folder structure as an example:

```cmd
├── pages
|  ├── index.js
|  ├── contact.js
|  └── my-folder
|     ├── about.js
|     └── index.js
```

## Deploying Your Next.js App

 `Vercel` A cloud platform for serverless deployment. It enables developers to host websites and web services that deploy instantly, scale automatically, and require no supervision, all with minimal configuration. Vercel is a tool in the Static Web Hosting category of a tech stack.

Deploy nextJS app to Vercel with the following steps:

1. Sign up to `Vercel`.
2. Create a new project.
3. import your Next.js app.
4. configure your app settings and environment variables.
5. deploy your app.

it’ll build and deploy create a preview url .
