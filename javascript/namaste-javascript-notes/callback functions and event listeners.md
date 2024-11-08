A **callback function** is a function that is passed as an argument to another function and is intended to be executed after a certain event or task is completed within the receiving function. This concept is widely used in programming languages like JavaScript, especially in asynchronous operations, where callbacks ensure that specific code runs only when needed.

Here's a simple breakdown of how it works:

1. **Define a Callback**: You create a function that performs a certain task.
2. **Pass it as an Argument**: You pass this function to another function as an argument.
3. **Invoke the Callback**: The receiving function then invokes this callback function at a specific point in its execution.

### Example in JavaScript

Let's look at an example using JavaScript, where callback functions are common in asynchronous programming.

```javascript
// Define a callback function
function greeting(name) {
    console.log(`Hello, ${name}!`);
}

// Define a function that takes another function as a parameter
function processUserInput(callback) {
    const name = "Alice";
    callback(name);
}

// Call processUserInput, passing 'greeting' as the callback
processUserInput(greeting);
```

In this example:
- `greeting` is a function that prints a greeting message.
- `processUserInput` is a function that takes a callback function as an argument and then calls that callback function with some data (`name`).
- When we call `processUserInput(greeting)`, it passes `greeting` to `processUserInput`, which then calls `greeting("Alice")`, printing `"Hello, Alice!"`.

### Why Use Callback Functions?

1. **Asynchronous Operations**: Callback functions allow handling tasks that take time, like API requests, file reading, or database operations, without blocking code execution.
2. **Separation of Concerns**: They enable separating the functionality of functions, allowing different functions to handle different tasks more cleanly.

### Example in Python

While callbacks are less common in Python, they can still be used, especially with functions like `map`, `filter`, or even custom functions.

```python
# Define a callback function
def greeting(name):
    print(f"Hello, {name}!")

# Define a function that takes another function as a parameter
def process_user_input(callback):
    name = "Alice"
    callback(name)

# Call process_user_input, passing 'greeting' as the callback
process_user_input(greeting)
```

This example mirrors the JavaScript one and achieves the same result.