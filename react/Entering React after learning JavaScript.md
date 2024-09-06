## Why learn React?

### Innovation
React can be integrated seamlessly with any other library or framework because React is a view only library, (it is the view part of the **M**odel **V**iew **C**ontroler [MVC](https://en.wikipedia.org/wiki/Model%E2%80%93view%E2%80%93controller) architectural UI pattern). The freedom to use any other framework and library makes it possible to experiment and so to innovate.

### Simple API
React has a relatively simple API and so has no steep learning curve. It only has a handful of methods to understand. The code to make ‘components’ of the UI (i.e., buttons etc) is straight-forward as there is very little boilerplate code which makes the library comparatively accessible.

### JavaScript
JavaScript is arguably the [world’s most popular programming language](https://www.businessinsider.com/14-most-popular-programming-languages-stack-overflow-developer-survey-2018-4) and is also incredibly powerful. JavaScript is both a functional and an object-oriented programming language and so harnesses the advantages brought by both paradigms. React is in JavaScript and so inherits its benefits.

### ES6
“[ES6](https://www.makeuseof.com/tag/es6-javascript-programmers-need-know/) refers to version 6 of the ECMA Script programming language. ECMA Script is the standardized name for JavaScript, and version 6 is the next version after version 5, which was released in 2011. It is a major enhancement to the JavaScript language, and adds many more features intended to make large-scale software development easier.” You can [read more](https://www.makeuseof.com/tag/es6-javascript-programmers-need-know/) for the details of the new features that ES6 introduces.

### JSX
JSX stands for **J**avascript **S**yntax **E**xtension. It allows you to use HTML and XML in JavaScript. Essentially, the HTML/XML code is ‘transpiled’ into JavaScript. In other words, the HTML/XML is converted into JavaScript before the code is compiled. This enables the full power of JavaScript to be employed with the relative ease of writing in HTML.

### Unidirectional Data Flow
React implements one-way data flow which makes it easy to reason about your app. Essentially all the parts of the UI are contained within each other which makes tracing data flow super simple.

### Community
React is a very popular and growing library. This means that the React community is large and growing too. So there are a plethora of resources out there to help you as you learn. Essentially, you won’t get ‘stuck’ anywhere for extended periods of time as someone will have had the same problem as you before and is likely to have posted about it online.


### Why bother learning JavaScript? Why not dive straight into React?
While it is possible to learn React without any knowledge of JavaScript, it won’t be easy. Frequent run-ins with language specific issues would become roadblocks. If you know JavaScript well, on the other hand, your React journey will be smooth, and the focus would be on utilizing the functionalities of React itself. 


# Ternary Operator in React
A ternary operator — also called Conditional Operator — is the only JavaScript operator which takes three operands and returns a value based on some condition. It’s an alternative for `if` statement. This could be used for multiple purposes and comes in very handy in React too!

Displaying JavaScript strings, objects, and arrays in React is not enough. What about an if-else statement for enabling _conditional rendering_? You cannot use an if-else statement directly in JSX, but you can return early from the rendering function. Returning `null` is valid in React when displaying nothing. Just like we did in the example given below.

>**Did you know?** Conditional rendering in React uses JavaScript operators like `if` or the conditional operator to create elements representing the current state, and let React show or hide a certain UI element based on a condition.


# Object Destructuring & Spread Operators
### What is Destructuring?

Another language feature introduced in JavaScript is called _[Object Destructuring](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Operators/Destructuring_assignment)_. It’s often the case that you have to access plenty of properties from your state or props in your component. Rather than assigning them to a variable one by one, you can use _destructuring_ assignment in JavaScript. See the following example for better understanding: 
Assume there is an object named `student` and you want to extract its properties, one way to do this is:

```js
const student = {

  ID: '21',

  name: 'Jhon',

  GPA: '3.0',

};

  

const id = student.ID;

const name = student.name;

const GPA = student.GPA;

  

console.log(id);

console.log(name);

console.log(GPA);
```

But as you can see, there’s a lot of repetitive code in this example. So, to make things simpler, we can rewrite this code as:

```js
const student = {

  ID: '21',

  name: 'Jhon',

  GPA: '3.0',

};

  

const {ID, name, GPA} = student;
```

Another example of destructuring could be
```js
// no destructuring

const users = this.state.users;

const counter = this.state.counter;

  

// destructuring

const { users, counter } = this.state;
```

### Spread Operator

Another JavaScript feature that we use quite a lot in React is the Spread Operator. Spread Operator literally spreads the contents of an array into its elements which makes operations like concatenation etc. easier. Let’s say we want to concatenate two arrays, we either do this by using `concat` function, like this:

```js
a = [1,2,3];

b = [4,5,6];

c = a.concat(b);

console.log("c: " + c);
```





