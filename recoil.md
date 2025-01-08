# Context API
- To avoid prop drilling, React introduced Context API.
- Prop Drilling : To pass the props to a certain child component of the application, the parent component needs to pass down the props to every child component between itself and the target child component. This is prop drilling. The intermediate child components didn't even need those props but just to pass them down, they have to take them.
- Using Context API, one can define their state variables outside the component tree. 
- (https://github.com/100xdevs-cohort-2/week-7) ![](attachments/Pasted%20image%2020240911211449.png)
- 3 Steps:
	- Define the context in a separate file.
	- Provide the context throughout the component chain.
	- `useContext` hook can be used to get the current value of the state variable.
- ![](attachments/Pasted%20image%2020240911211653.png)
- Problem with Context API : Even the components which do not contain the state variables are re-rendered. This is why we use state management libraries like Recoil. Context API only helps in getting rid of prop drilling and writing a cleaner code, but the rendering is not more performant.

# Recoil
- A state management library for React
Recoil is a state management library for React, designed by Facebook to simplify state handling in complex applications. It provides a more flexible and efficient way to manage global state compared to traditional approaches like Redux. Here are some key features and concepts in Recoil:

### Key Features of Recoil

1. **Atoms**: Atoms are units of state that can be shared across components. They represent pieces of state that can be read and written independently, allowing fine-grained updates.

2. **Selectors**: Selectors are functions that derive state based on atoms or other selectors. They provide a way to transform or compute state on-demand, and their values are cached until any of their dependencies change.

3. **Asynchronous Data**: Recoil has built-in support for asynchronous data flows. You can easily use selectors to fetch or derive asynchronous data without having to manage loading or error states manually.

4. **Reactivity and Efficiency**: Recoil is reactive by design. When an atom or selector’s value changes, only the components that depend on that specific piece of state re-render, which improves performance.

5. **Hooks**: Recoil offers custom hooks like `useRecoilState`, `useRecoilValue`, and `useSetRecoilState` for interacting with atoms and selectors, making it easy to read, write, and track state in functional components.

### Basic Example of Recoil

Here’s a quick example to demonstrate how to set up Recoil and use atoms and selectors:

1. **Install Recoil**:

   ```bash
   npm install recoil
   ```

2. **Set Up a Recoil Root**: Wrap your app in a `RecoilRoot` component to provide Recoil state management to your components.

   ```javascript
   import { RecoilRoot } from 'recoil';
   import App from './App';

   function Root() {
     return (
       <RecoilRoot>
         <App />
       </RecoilRoot>
     );
   }
   ```

3. **Define an Atom**:

   ```javascript
   import { atom } from 'recoil';

   const textState = atom({
     key: 'textState', // unique ID (with respect to other atoms/selectors)
     default: '', // default value (initial value)
   });
   ```

4. **Use the Atom in a Component**:

   ```javascript
   import React from 'react';
   import { useRecoilState } from 'recoil';
   import { textState } from './atoms';

   function TextInput() {
     const [text, setText] = useRecoilState(textState);

     const handleChange = (event) => {
       setText(event.target.value);
     };

     return (
       <div>
         <input type="text" value={text} onChange={handleChange} />
         <p>Current Text: {text}</p>
       </div>
     );
   }
   ```

5. **Define a Selector**:

   ```javascript
   import { selector } from 'recoil';
   import { textState } from './atoms';

   const charCountState = selector({
     key: 'charCountState',
     get: ({ get }) => {
       const text = get(textState);
       return text.length;
     },
   });
   ```

6. **Use the Selector in a Component**:

   ```javascript
   import React from 'react';
   import { useRecoilValue } from 'recoil';
   import { charCountState } from './selectors';

   function CharacterCount() {
     const count = useRecoilValue(charCountState);
     return <p>Character Count: {count}</p>;
   }
   ```

By combining atoms and selectors, Recoil makes it easy to manage, compute, and display state across components. It’s especially useful in large applications with complex state requirements, providing both fine-grained control and efficiency.