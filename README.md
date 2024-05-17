# Single-Page Application Routing

## Multiple Pages in Single-Page Apps

- What Client Side Routing is & Why Use it?
- Using React Router
- Data Fetching & Submission

# Steps

## 0. Starting Project

1. create a new `README.md` file
2. run `npm install react-router-dom`
3. add a new `.gitignore` file & put `node_modules` inside

## 1. Defining Routes

1. in `App.js`, use `createBrowserRouter` imported from `react-router-dom`
2. define the routes inside of this function
3. add a new `pages` folder to hold the components that will be loaded as pages by the router
4. inside of it, add a new `Home.js` file that contains the `HomePage` component
5. in `App.js`, load the `HomePage` component when the `/` route is active with help of the `element` key property to establish the connection inside the `createBrowserRouter` function
6. in `App.js`, use this `/` router:
   1. store the returned value of the `createBrowserRouter` function in a `router` constant
   2. use the `RouterProvider` component imported from `react-router-dom` to tell React that this `/` router should be loaded & should render the appropriate pages to the screen
   3. set to it the special `router` prop & pass to it the `router` constant as a value
7. run `npm start` to start the development server to see the content of the `<HomePage>` component rendered by the `/` router
