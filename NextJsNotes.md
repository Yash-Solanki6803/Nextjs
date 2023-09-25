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
  return <div>Welcome to Next.js!</div>;
}

export default HomePage;
```

#### About and Profile Page

Lets assume that we want to create a route for the `/about` route , we just have to create a file with the name `about.js` in the `pages` folder.

```js
function AboutPage() {
  return <div>About Page</div>;
}

export default AboutPage;
```

Same goes for the `/profile` route , we just have to create a file with the name `profile.js` in the `pages` folder.

```js
function ProfilePage() {
  return <div>Profile Page</div>;
}

export default ProfilePage;
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
  return <div>Blog Page</div>;
}

export default BlogPage;
```

```js
function FirstBlogPage() {
  return <div>First Blog Page</div>;
}

export default FirstBlogPage;
```

```js
function SecondBlogPage() {
  return <div>Second Blog Page</div>;
}

export default SecondBlogPage;
```

Now you must have thought why do we need to keep the blog.js file in the pages folder whereas the first.js and second.js files are in the blog folder.

A simple solution to this problem is to move the blog.js inside the blog folder and rename it to index.js.

Thus the folder structure will be as follows:

- blog/index.js
- blog/first.js
- blog/second.js

### Dynamic routes

Lets say we want to create a route for the following:

- localhost:3000/blog/1
- localhost:3000/blog/2
- localhost:3000/blog/3
- localhost:3000/blog/4
- localhost:3000/blog/5
- localhost:3000/blog/6
- localhost:3000/blog/7
- localhost:3000/blog/8

Thus in order to create these routes , we have to create the following files in the `pages` folder:

- blog/[id].js
- blog/1.js
- blog/2.js
- blog/3.js
- blog/4.js
- blog/5.js
- blog/6.js
- blog/7.js
- blog/8.js
- blog/9.js

Here the [id].js file is a dynamic route.

Thus the `blog/[id].js` file will be the parent route and the `blog/1.js` , `blog/2.js` , `blog/3.js` , `blog/4.js` , `blog/5.js` , `blog/6.js` , `blog/7.js` , `blog/8.js` and `blog/9.js` files will be the child routes.

```js
function BlogPage() {
  return <div>Blog Page</div>;
}

export default BlogPage;
```

```js
import { useRouter } from "next/router";

function BlogIdPage() {
  const router = useRouter();
  const { id } = router.query;

  return <div>Blog {id} Page</div>;
}

export default BlogIdPage;
```

### Nested Dynamic routes

Lets say we want to create a route for the following:

- localhost:3000/blog/1/review/1

Thus in order to create these routes , we have to create the following files in the `pages` folder:

- blog/[id]/review/[id].js

Thus in order to create dynamic pages we named the file by using `[]` so that it can be dynamic. Now for making nested dynamic pages we will use `[]` to name the folder.

Thus the `blog` folder will have a folder named `boldId` which will have a file named `index.js` and a folder named `review` which will have a file named `[reviewId].js`.

Thus the folder structure will be as follows:

- blog/[id]/index.js
- blog/[id]/review/[reviewId].js

Inside [reviewId].js we will have the following code:

```js
import { useRouter } from "next/router";

function Review() {
  const router = useRouter();
  const { BlogId, reviewId } = router.query;

  return (
    <div>
      <h1>
        Blog {BlogId} Review {reviewId}
      </h1>
    </div>
  );
}
```

### Catch-all routes

Lets say we want to create a route for the following:

- localhost:3000/blog/1/example1/etcetc
- localhost:3000/blog/2/example2/etcetc
- localhost:3000/blog/3//example3/etcetc

Thus in order to create these routes , we have to create the following files in the `pages` folder:

- blog/[...id].js
- blog/1.js
- blog/2.js
- blog/3.js

Here the [...id].js file is a catch-all route. That means even if the user types anything after the id , it will still be routed to the same page.

Thus a route like `localhost:3000/blog/1/example1/etcetc` will be routed to the `blog/[...id].js` file.

Thus the `blog/[...id].js` file will be the parent route and the `blog/1.js` , `blog/2.js` and `blog/3.js` files will be the child routes.

```js
function BlogPage() {
  return <div>Blog Page</div>;
}

export default BlogPage;
```

```js
import { useRouter } from "next/router";

function BlogIdPage() {
  const router = useRouter();
  const { id } = router.query;

  return <div>Blog {id} Page</div>;
}

export default BlogIdPage;
```

Now if the url has more than one parameter than the `router.query` will return an array.

Thus in this case the `router.query` will return an array of the parameters after the id.
i.e. `[example1,etcetc]`

### Navigate from the UI

In order to navigate from the UI , we have to use the `Link` component from the `next/link` package.

```js
import Link from "next/link";

function HomePage() {
  return (
    <div>
      <Link href="/about">
        <a>About</a>
      </Link>
    </div>
  );
}

export default HomePage;
```

### Programmatically navigate b/w Pages

In order to programmatically navigate b/w pages , we have to use the `useRouter` hook from the `next/router` package.

```js
import { useRouter } from "next/router";

function HomePage() {
  const router = useRouter();

  const handleClick = () => {
    router.push("/about");
  };

  return (
    <div>
      <button onClick={handleClick}>About</button>
    </div>
  );
}

export default HomePage;
```

## Data Fetching and Pre-rendering

### Pre-rendering

Pre-rendering is the process of generating HTML at build time instead of request time.

There are two types of pre-rendering:

- Static Generation
- Server-side Rendering

By default , NEXT.js pre-renders every page in your app.

### Why pre-render?

1. Pre-rendering improves performance.
   - In React app, you need to wait for the JS to be executed.
   - Perhaps fetch fata from an external API and then render the UI.
   - There is a wait time for the user to see the page. This is called the `First Contentful Paint`.
   - Pre-rendering allows you to generate the HTML at build time and then reuse it on each request.
   - With a pre-rendered page, the user can see the page immediately.
2. Pre-rendering helps with SEO
   - Search engines can crawl and index the page.
   - With a React app, if the search engine hits your page , it only sees a div tag with id = root.
   - With a pre-rendered page, the search engine can see the HTML content.
   - This helps with SEO.

### Static Generation

Static Generation is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request.

Static Generation is the pre-rendering method that generates the HTML at build time. The pre-rendered HTML is then reused on each request.

Pages can be built once, cached by a CDN and served to the client without having to rebuild them on each request.

**NOTE**: Pre-rendering occurs every time you run the build command. But for the development server , pre-rendering occurs every time you make a request.

Static Generation can be done with and without data.

#### Static Generation without data

If a page does not have any data requirements, then it can be pre-rendered without any data.

```js
function HomePage() {
  return <div>Welcome to Next.js!</div>;
}

export default HomePage;
```

#### Static Generation with data

If a page has data requirements, then it can be pre-rendered with data.

```js
function HomePage(props) {
  return <div>Welcome to {props.data.name}!</div>;
}

//This function will run at build time on the server side. It is required to call it  as `getStaticProps`.
export async function getStaticProps() {
  const res = await fetch("https://jsonplaceholder.typicode.com/users");
  const data = await res.json();

  //It is convention to return an object with a property  called `props` which contains the data.
  return {
    props: {
      users: data,
    },
  };
}

export default HomePage;
```

#### Pages vs Components

Pages are different from components.

Pages are associated with routes based on their file name.

Components are not associated with routes.

When a page with getStaticProps is pre-rendered ay build time , in addition to the page HTML file, Next.js generates a JSON file holding the result of running getStaticProps.

The JSON file is used in client-side routing through next/link.

When you navigate to a page that's pre-rendered using getStaticProps, Next.js fetches the JSON file (pre-computed at build time) and uses it as the props to create the page component client-side.

Client-side page transitions will not call getStaticProps as only the exported JSON is used.

#### Static generation Summary so far...

Static Generation is a method of pre-rendering where the HTML pages are generated at build time

With and without external Data

Export getStaticProps function for external data

HTML, Javascript and a JSON file are generated

If you navigate directly to the page route , the HTML file is served

If you navigate to the page route from a different route, the page is created client side using the JavaScript and JSON prefetched from the server.

#### Static Generation with dynamic Parameters

If a page has dynamic parameters , then it can be pre-rendered with data.

```js
function BlogIdPage(props) {
  return <div>Blog {props.data.id} Page</div>;
}

export async function getStaticProps(context) {
  const { params } = context;
  const { id } = params;

  const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
  const data = await res.json();

  return {
    props: {
      data: data,
    },
  };
}
```

But this will only work for the dynamic routes that are defined in the `pages` folder.

Thus if we want to create a route for the following:

- localhost:3000/blog/1

Thus in order to create these routes , we have to create the following files in the `pages` folder:

- blog/[id].js

But this UserID can be anything. So we have to tell Next.js that this is a dynamic route and also tell it the possible values of getStaticProps function.

Thus we will create a `getStatcPaths` function.

So inside [id].js we will have the following code:

```js
function BlogIdPage(props) {
  return <div>Blog {props.data.id} Page</div>;
}

export async function getStaticPaths() {
  //you can also fetch data from an API here and map over it to create the paths array dynamically
  return {
    paths: [
      { params: { id: "1" } },
      { params: { id: "2" } },
      { params: { id: "3" } },
      { params: { id: "4" } },
      { params: { id: "5" } },
      { params: { id: "6" } },
      { params: { id: "7" } },
      { params: { id: "8" } },
      { params: { id: "9" } },
    ],
    fallback: false,
  };
}

export async function getStaticProps(context) {
  const { params } = context;
  const { id } = params;

  const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
  const data = await res.json();

  return {
    props: {
      data: data,
    },
  };
}
```

#### getStaticPaths and fallback

The `getStaticPaths` function is used to tell Next.js the possible values of the dynamic parameters.

The `fallback` property is used to tell Next.js what to do if the user tries to access a page that is not pre-rendered.

If fallback is set to `false`, then Next.js will show a 404 page if the user tries to access a page that is not pre-rendered.

If fallback is set to `true`, then :

- The paths returned from getStaticPaths will be rendered to HTML at build time.
- The paths that have not been generated at build time will not result in 404 page. Instead, Next.js will serve a "fallback" version of the page on the first request to such a path.
- In the background, Next.js will statically generate the requested path HTML and JSON. This includes running getStaticProps.
- When that's done, the browser receives the JSON for the generated path. This will be used to automatically render the page with the required props. From the user's perspective, the page will be swapped from the fallback page to the full page.
- At the same time, Next.js adds this path to the list of pre-rendered pages. Subsequent requests to the same path will serve the generated page, just like other pages pre-rendered at build time.
- If the static generation fails at runtime, the request will trigger a 404 page.

If fallback is set to `blocking`, then Next.js will try to generate the page on the server side. If the page is not generated on the server side, then Next.js will show a 404 page.

#### Static Generation and Issues

Static Generation is a method of pre-rendering where the HTML pages are generated at build time

With and without external Data

Issues:

- If you have a lot of pages, it can take a long time to build

- A page once Generated , can contain stale data till the time you rebuild the app.

Thus to solve this problem , NEXT.js provides a feature called `Incremental Static Regeneration`.

### Incremental Static Regeneration

Incremental Static Regeneration is a feature that allows you to update existing pages by re-rendering them in the background as traffic comes in.

In the getStaticProps function , we can set a `revalidate` property which is the number of seconds after which a page re-generation can occur.

```js
export async function getStaticProps(context) {
  const { params } = context;
  const { id } = params;

  const res = await fetch(`https://jsonplaceholder.typicode.com/users/${id}`);
  const data = await res.json();

  return {
    props: {
      data: data,
    },
    revalidate: 10,
  };
}
```

This will re-generate the page after every 10 seconds.
