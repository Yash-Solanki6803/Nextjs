# Next.js Notes

## What is Next.js?

Next.js is a React framework that allows you to build server-side rendered (SSR) React applications. It is built on top of React, Webpack, and Babel.

## Why Next.js?

Next.js is a great framework for building React applications. It provides a lot of features out of the box, such as:

- Server-side rendering
- File-based routing
- Automatic code splitting
- Static site generation
- API routes
- TypeScript support
- CSS-in-JS support
- Zero-config
- Fast refresh
- Customizable Babel and Webpack configurations
- Automatic polyfills
- Automatic routing based on file system
- Automatic code splitting for faster page loads
- Static file serving. Including serving React components as static HTML
- CSS and Sass support
- Built-in CSS and Sass support, and support for any CSS-in-JS library
- Fast refresh preserves React state in functional components, and this is achieved by automatically wrapping your entire application in React Refresh

## Pre-requisites

- Really good knowledge of HTML,CSS and JavaScript
- ES6+ features
- Really good knowledge of React

## How to install Next.js?

To install Next.js, you can use the following command:

- To do it manually you can do :
```bash
npm install next react react-dom
```

- To do it automatically you can do:
```bash
npx create-next-app
```


## How to run Next.js?

To run Next.js, you can use the following command:

```bash
npm run dev
```

## How to build Next.js?

To build Next.js, you can use the following command:

```bash
npm run build
```

## How to deploy Next.js?

To deploy Next.js, you can use the following command:

```bash
npm run start
```

## How to create a Next.js app?

To create a Next.js app, you can use the following command:

```bash
npx create-next-app
```

## How to create a Next.js app with TypeScript?

To create a Next.js app with TypeScript, you can use the following command:

```bash
npx create-next-app --typescript
```

## How to create a Next.js app with Tailwind CSS?


To create a Next.js app with Tailwind CSS, you can use the following command:

```bash
npx create-next-app --example with-tailwindcss
```

## After creating a Next.js app, what are the files and folders that are created?

After creating a Next.js app, a few folders are created. The main ones are:

- .next: This folder contains the build files for your Next.js app.
- src: This folder contains the source code for your Next.js app.
- public: This folder contains the public files for your Next.js app.


### What is the difference between the public folder and the src folder?

The public folder contains the public files for your Next.js app. The src folder contains the source code for your Next.js app.

The `public` folder contains your assets.

The `src` folder contains the pages folder , styles or the components folder depending upon the developer's choice.


The `pages` folder contains the pages of your app as well as the `api` folder which contains the api routes.

The `styles` folder contains the global styles of your app.

The main code of the app is in the `pages/index.js` file.

## Routing

### React Routing

In react , routing is done using the `react-router-dom` package.

Thus in order to route to a particular page , we had to go through the following steps:

- Install the `react-router-dom` package.
- Import the `BrowserRouter` and `Route` components from the `react-router-dom` package.
- Wrap the `App` component with the `BrowserRouter` component.
- Use the `Route` component to render the component for a particular route.
- Use the `Link` component to create a link to a particular route.

Thus it is obvious that this is a tedious process.

### Next.js Routing

In Next.js , routing is done automatically.

Thus in order to route to a particular page , we just have to create a file with the name of the route in the `pages` folder.

Thus if we want to create a route for the `/about` route , we just have to create a file with the name `about.js` in the `pages` folder.

Thus it is obvious that this is a very easy process.

So in this module we will discuss about the following:

- Route with Pages
- Nested routes
- Dynamic routes
- Catch-all routes
- Navigate from the UI
- Programmatically navigate b/w Pages

### Route with Pages


Next has a file based routing system.

Thus in order to route to a particular page , we just have to create a file with the name of the route in the `pages` folder.

#### Home Page

Thus if we want to create a route for the `/` route , we just have to create a file with the name `index.js` in the `pages` folder.

```js
function HomePage() {
  return <div>Welcome to Next.js!</div>
}

export default HomePage
```

#### About and Profile Page

Lets assume that we want to create a route for the `/about` route , we just have to create a file with the name `about.js` in the `pages` folder.

```js
function AboutPage() {
  return <div>About Page</div>
}

export default AboutPage
```

Same goes for the `/profile` route , we just have to create a file with the name `profile.js` in the `pages` folder.

```js
function ProfilePage() {
  return <div>Profile Page</div>
}

export default ProfilePage
```
Thus in NEXT pages are associated routes on the basis of the file name.




### Nested routes

Lets say we want three routes : 

- localhost:3000/blog
- localhost:3000/blog/first
- localhost:3000/blog/second

Thus in order to create these routes , we have to create the following files in the `pages` folder:

- blog.js
- blog/first.js
- blog/second.js

Here the first.js and second.js files are nested in side the blog folder.
  
Thus the `blog.js` file will be the parent route and the `blog/first.js` and `blog/second.js` files will be the child routes.

```js
function BlogPage() {
  return <div>Blog Page</div>
}

export default BlogPage
```

```js
function FirstBlogPage() {
  return <div>First Blog Page</div>
}

export default FirstBlogPage
```

```js
function SecondBlogPage() {
  return <div>Second Blog Page</div>
}

export default SecondBlogPage
```

Now you must have thought why do we need to keep the blog.js file in the pages folder whereas the first.js and second.js files are in the blog folder.

A simple solution to this problem is to move the blog.js inside the blog folder and rename it to index.js.

Thus the folder structure will be as follows:

- blog/index.js
- blog/first.js
- blog/second.js

### Dynamic routes

