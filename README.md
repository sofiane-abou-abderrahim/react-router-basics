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

## 2. Adding a Second Route

1. add a new `Products.js` component inside the `pages` folder
2. in `App.js`, add a route for the `ProductsPage` component

## 3. Exploring an Alternative Way of Defining Routes

1. in `App.js`, call the `createRoutesFromElements` function imported from `react-router-dom`
2. store its returned value in a constant called `routeDefinitions`
3. add a `<Route>` component imported from `react-router-dom` as an argument to this function
4. inside this `<Route>` component, add your nested route with a `path` & an `element` props
5. call the `createBrowserRouter` function & pass the `routeDefinitions` constant to it as an argument
6. store the returned value of this function to a constant named `router`
7. pass this constant as a value to the `router` prop of the `<RouterProvider>` component

## 4. Navigating between Pages with Links

1. don't use the `<a>` so that you don't send HTTP requests when navigating
2. in `Home.js`, instead, use the `<Link>` component imported from `react-router-dom` to navigate to the other pages

## 5. Layouts & Nested Routes

1. add a navigation bar to navigate to the pages
   1. add a new `components` folder
   2. inside of it, add a new `MainNavigation.js` file
2. add some layout that wraps all these routes to render the main navigation
   1. add a new `Root.js` file in the `pages` folder
   2. add a new root in `App.js` & render the `<RootLayout>` component
   3. add a special `children` property to wrap the other routes with this `<RootLayout>` component
   4. in `Root.js`, use the `Outlet` component imported from `react-router-dom` to define where these child routes should be rendered
   5. include the `<MainNavigation>` component above the `<Outlet>` component in `Root.js`
3. apply some styling
   1. add a new `Root.module.css` file
   2. add a new `MainNavigation.module.css` file

## 6. Showing Error Pages with errorElement

1. add a new `Error.js` file in the `pages` folder
2. add the special `errorElement` property to the route definitions in `App.js` to render the `<ErrorPage>` component

## 7. Working with Navigation Links (NavLink)

1. replace the `<Link>` component with the `<NavLink>` component to let the link active after we click on it
2. add the `className` prop to the `<NavLink>` component
3. set a function to `className` where you pass to it the `isActive` property provided by `react-router-dom`
4. add the `end` prop to the home link so that the CSS class applies only when the path ends with `/` and not when it begins with
