# React Calculator

![calc](https://cdn.dribbble.com/users/2184773/screenshots/4516857/calculator.gif)

## Overview
Now, it's time for you to check back on everything! You will be building a
calculator with React, and only minimal instructions have been provided for you to really think about what's happening.

At first, your calculator will just add 2 numbers
together when they are typed in. For the bonus, you might decide to get more
creative.

## Getting Started
- `Fork` and `clone` this repository and `cd` into the new directory
- Like usual, use `npx create-react-app simple-calculator` to make a new project.
- `cd` into your new React app
- Create a `components` folder within the `src` directory to store any components we'll create in this deliverable
- `npm start` to start up your new React app


## Instructions
### Step 1
Start by replacing `App.js` with this component structure:
```js
  import React, { Component } from 'react';
  import './App.css';

  class App extends Component {
    render() {
      return (
        <div className="App">
          <h1>Add With React!</h1>
          
          // Your <Calculator /> component here
        </div>
      );
    }
  }
  
  export default App;
```


Next we'll by create a single `Class` component file in the `components` directory, and name it
`Calculator.js`. 

- In this file, create your `Calculator` class component. 
-  Add the following JSX to the return of your Calculator's `render()` function:

```html
<div className="container">
  <div className="add">    
    <input type="text" />
    <span>+</span>
    <input type="text" />
    <button>=</button>
  </div>
  <h3 className="results">Addition results go here!</h3>
</div>
```
- If you want a quick CSS snippet to make your app more visible, you can find it here:
<details><summary>App.css</summary>
  
  ```css
  body {
    background-color: rgb(136, 255, 182);
  }

  .App {
    text-align: center;
  }

  input, button {
    border: none;
    font-size: 1.2em;
    border-radius: 0.25em;
    padding: 0.5em;
    outline: none;
  }

  button, h1 {
    background-color: rgb(37, 37, 37);
    color: white;
    font-weight: bold;
    box-shadow: 0px 0px 5px black;
  }

  button:active {
    box-shadow: none;
  }

  input:focus {
    box-shadow: inset 0px 0px 6px rgb(175, 0, 73);
  }

  input {
    box-shadow: inset 0px 0px 3px black;
    width: 8em;
  }

  h1 {
    padding: 0.5em;
    margin-top: 0;
    margin-bottom: 2em;
  }

  button {
    padding: 0.5em 1.5em;
  }

  .add {
    display: flex;
    justify-content: space-around;
  }

  .add > span {
    font-size: 2em;
    font-weight: bold;
  }

  .container {
    width: 30em;
    margin: 0 auto;
    background-color: rgb(173, 208, 255);
    padding: 2em;
    border-radius: 0.5em;
    box-shadow: 0px 0px 5px black;
  }

  .results {
    background-color: white;
    padding: 2em;
    width: 21em;
    margin: 1em auto 0 auto;
    border-radius: 0.25em;
    box-shadow: inset 0px 0px 3px black;
  }
  ```
</details>

- Make sure to `import` your `Calculator` component into `App.js`!

### Step 2
Set up the initial state of your component. What state attributes will you
need to track? What values should those state items start with? Where is that
state displayed in the browser?

> Hint: You will only need one state. That one state can hold as many key-value pairs as you need!

### Step 3
You will want to trigger a function when the values in your textboxes change. You can capture these values by setting a function on the onChange property. Let's say I have a textbox tracking my first number.

```
<input type="number"
  name="num1"
  placeholder="Enter your first number"
  value={this.state.num1}
  onChange={ (e) => this.setNum(e, 'num1') }
/>
```

I want to store this number as part of my state. Let's say I decided to call it `num1`. I could set my state like so:

```
setNum = (e, num) => {
  this.setState({ [num]: e.target.value});
}
```

> Hint: The [] are there so we can use a dynamic key value! This value becomes `num1` or `num2` depending on what was clicked and sent to the function from `onChange`.

If you decided to use buttons for your calculator, you probably want to use `onClick` instead of `onChange`, but the concepts are the same! Here is some documentation to help you choose what you want to do and how to do it:

* [React form documentation](https://facebook.github.io/react/docs/forms.html)
* [A list of events React supports](https://facebook.github.io/react/docs/events.html#supported-events)


### Step 4
Once you've got your event handlers set up to capture the input, you'll need to create a
method for your submit button. The method should accept the triggered event, get the input values from
your state, add them together, and set part of the state to the new `sum`.

<details>
  <summary>Hint: Where should this method go?</summary>
  <p>In the same component as it's being used - between the constructor and the render.</p>
</details>

> Thought: How will you handle inputs that aren't numbers?

### Step 5
Once the state of the `sum` has been set, React will re-render the whole
component. Make sure you have a place in your JSX that displays the result!

## Requirements

## Bonus

- Make the calculator work with any of the 4 basic arithmetic operations
(+, -, \*, /). How will this change your `state` and your JSX?


## Submission Guidelines
- Pull Request must be submitted utilizing these guidelines: [PR Guidelines](https://github.com/SEI-R-1-25/template_pull_request)

## Resources
- [React State Intro Lesson](https://github.com/SEI-R-1-25/u2_lesson_react_state_intro)
- [React Todo List Lab](https://github.com/SEI-R-1-25/u2_lab_react_todos)
- [React Lifecycle Methods Lesson](https://github.com/SEI-R-1-25/u2_lesson_react_lifecycle)

