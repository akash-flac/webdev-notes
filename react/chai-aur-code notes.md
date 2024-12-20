# React intro
- React is a library.(https://react.dev/)
- Topics to learn :
	- core of React(state or UI manipulation, JSX)
	- component reusability
	- reusing of component
	- how to propagate change
- additional stuff in react
	- router(react doesn't have an in-built router)
	- state management(react doesn't have state management)
		- redux, redux toolkit, zustand, context api
	- class based components(legacy code)
	- BAAS(backend as a service) apps

Two ways to install react:
- create-react-app : `npx create-react-app reactProjectName`
- vite : `npm create vite@latest` and use `npm install` to install node modules within the proj

> It's a good practice to begin with analyzing the `package.json` file at first.

# React flow and Structure
- React helps in building SPA(single-page applications).
- `index.html` file is the main page which is loaded, the single page of the SPA.
- The default entry point for a React application is `index.js` or `main.jsx` file within the `src` folder.
- The following flow is wrt to `create-react-app` ![](attachments/Pasted%20image%2020240908151345.png) `index.html` : here, we have div with id="root".  the id could be named anything. this is where the application is rendered.
- ![](attachments/Pasted%20image%2020240908152418.png) `App.js` : We create a component here and export it. Here, within a javascript function, we contain an html element. 
- ![](attachments/Pasted%20image%2020240908151544.png)`index.js` : here, we "get" the ID of the div where we want to render the component. We create a virtual DOM element wrt to the actual DOM, and render it.  This happens with the help of jsx syntax. We return html elements in JS functions(which are called components). We import `App` and use render function, and render `App` at the div with `id = "root"`. `<App />` is used to do so. We can just call this a custom html tag, using which we are rendering this component(JS function within this file). In case of virtual DOM, a virtual DOM is created by React, which is compared with the actual DOM of the index.html file, and only those components which are changed are rendered and updated.
- ![](attachments/Pasted%20image%2020240908154037.png) `package.json` : here, within dependencies, we have testing libraries, which are not needed unless one is making a production-grade application. apart from that, react and react-dom are needed to build web applications using React. `react-scripts` adds additional code to the `index.html` file when running it. It adds `main.js` or `index.js` to the main `index.html` file. But this is only true for `create-react-app` and not vite. 
- VITE RULES : 
	- In case of Vite, `react-scripts` isn't needed and instead, a `script` tag is used in the `index.html` file itself to load the `main.jsx` file. 
	- Apart from that, JS files always need to have the extension `.jsx` and not `.js` because in Vite, jsx refers to a React component. 
	- Another this is that that the first letter of the component function name needs to be capitalized. These are just best practices.

# Creating your own React library and JSX
- https://youtu.be/kAOuj6o7Kxs?si=qxIZA_qUVdUq9Wiw (from 38:35)

# Hooks
- Hooks are required to propagate changes to the UI. Eg. If something is updated according to the logic of the program, such as addition of 2 numbers, then for the change to propagate, we use `useState` hook.
- ![](attachments/Pasted%20image%2020240908192708.png) Here, we use `useState` hook. count is the variable in which hook makes changes, and setCount is the function using which the changes to the count variable are updated and propagated in the UI. Whatever the value we pass through setCount, that becomes the value of count on the UI.  ![](attachments/Pasted%20image%2020240908192924.png) 
# Virtual DOM, Fiber and Reconciliation
## Virtual DOM

 The virtual DOM (Virtual Document Object Model) is a programming concept in which a "virtual" representation of a user interface is preserved in memory and synchronized with the browser's DOM (Document Object Model) via a library. Instead of directly updating the actual DOM (Document Object Model), which can be slow and inefficient due to reflows and repaints, a virtual representation of the DOM is created in memory.
 
How the Virtual DOM works:
 - **Rendering the UI**: The Virtual DOM is a lightweight JavaScript object that mirrors the actual DOM structure. When a UI component changes, instead of updating the real DOM, React updates the Virtual DOM first.
 - **Diffing Algorithm**: React uses a diffing algorithm to compare the new Virtual DOM with the previous version. It identifies which parts of the UI have changed.
 - **Reconciliation**: Once the differences are identified, React selectively updates only the parts of the real DOM that changed, rather than re-rendering the entire UI.

# React Fiber
https://github.com/acdlite/react-fiber-architecture

# Tailwind and Props

## Props
- Props are arguments passed into React components.
- Props are passed to components via HTML attributes.
- props stand for properties.

![](attachments/Pasted%20image%2020240908200605.png)
- `props` is the default keyword which refers to the arguments passed to that particular function(or component). As we can call(or render) a certain component in React like an HTML custom tag, we can also add some arguments just like attributes of an HTML tag. These 'attributes' of this custom HTML tag are passed as props in the actual component function. `props` is the keyword used, but we can also use destructuring wherein we won't need to use the keyword `props`. Eg. `function Card({username})` instead of `function Card(props)`, where we can just write `username` in the function and no errors will be thrown, instead of `props.username` in case of no destructuring.

React Props are like function arguments in JavaScript _and_ attributes in HTML.
To send props into a component, use the same syntax as HTML attributes:
```jsx
const myElement = <Car brand="Ford" />;
```


```jsx
function Car(props) {
  return <h2>I am a { props.brand }!</h2>;
}

OR

function Car({brand}) {
  return <h2>I am a { brand }!</h2>;
}
```

# React Router
React Router enables "client side routing".

In traditional websites, the browser requests a document from a web server, downloads and evaluates CSS and JavaScript assets, and renders the HTML sent from the server. When the user clicks a link, it starts the process all over again for a new page.

Client side routing allows your app to update the URL from a link click without making another request for another document from the server. Instead, your app can immediately render some new UI and make data requests with `fetch` to update the page with new information.

This enables faster user experiences because the browser doesn't need to request an entirely new document or re-evaluate CSS and JavaScript assets for the next page. It also enables more dynamic user experiences with things like animation. 

Client side routing is enabled by creating a `Router` and linking/submitting to pages with `Link` and `<Form>`:
(example)
```jsx
import * as React from "react"; 
import { createRoot } from "react-dom/client"; 
import { createBrowserRouter, RouterProvider, Route, Link, } from "react-router-dom"; 
const router = createBrowserRouter([ 
	{ 
	path: "/", 
	element: (
	 <div> 
	 <h1>Hello World</h1> 
	 <Link to="about">About Us</Link>
	  </div> 
	  ), 
	}, 
	  { 
	  path: "about", 
	  element: <div>About</div>, 
	  }, 
	  ]); 
	  
 createRoot(document.getElementById("root")).render( 
 <RouterProvider router={router} /> 
 );
```

![](attachments/Pasted%20image%2020240910193110.png)
![](attachments/Pasted%20image%2020240910193120.png)
Here, to switch pages at the same URL, we use routing. React-router is used for this specific purpose. 

For this purpose, we design the structure of our project in this way. 
![](attachments/Pasted%20image%2020240910193417.png)
We keep a separate components folder wherein we store all the components separately. We create a router in the `main.jsx` file and use it for routing between the pages. `Layout.jsx` file is created to create a certain structure of the UI. 

- ![](attachments/Pasted%20image%2020240910193727.png)
`main.jsx` : Here, we create the browser router and use it for routing between the pages of the webpage. The syntax is given. This is one way. There is another way. It's given below.
![](attachments/Pasted%20image%2020240910194006.png)

 ![](attachments/Pasted%20image%2020240910194117.png) 
 - `Layout.jsx` : We use this file to have a certain structure for the UI. What we're trying to do here is have a separate header at the top and footer at the bottom, and only the components in between them are changed, as the header and footer are common in all.
























