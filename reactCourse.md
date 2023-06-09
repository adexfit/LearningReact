# Javascript refresher
+ let : variables that you will change
+ const : for constant values


+ jsbin.org
    - an online website where you can easily write javascript.

## Import/Export modules
    - Example
        - in file person.js
            const person = {
                name: 'Max'
            } 

            export default person

            - anything marked with the default keyword can be imported with any name.

        - in file utility.js 
            export const clean = () = {}
            export const baseData = 10;
        
        - in file app.js
            import {baseData} from './utility.js'
            import {clean} from './utility.js' 
            import {clean as Clean} from './utility.js' 
            import  * as bundled from './utility.js'

## Create new react project
+ npx create-react-app myApp

## Start a project on local host 3000
+ npm start

## Install dependencies in package.json
+ npm install

## Analyzing files inside index.js
+ index.js is the first file that is executed when we start the project.
+ the index.html is the only html file which is the single entry point where we have a div with the id root

## specifying file directory
+ You start specifying the directory from the file you are working on where you want to import the file. 
+ ./ means it should look into the same folder where the document we are working on is located
+ To go out of the folder upward '../'

## JSX
+ Stands for javascript XML
+ The return block in JSX is using this behind the hood
    React.createElement(`div`,{}, );

## Components
+ Your components must start with uppercase characters
+ React assumes that lowercase charcters are built-in characters while uppercase characters are written by you.
+ components help reuseability
    - separation of concern
    - Don't repeat yourself

## Styling Components
+ You create a css file for each component
+ import them inside their component.
+ use className instead of class. Class is a reserved word in javascript. 
+ How to import css file
    import './ExerciseComponent.css'

## Using javascript in react
+ You write javascript inside curly braces above return block.

## State in react
+ This should be added at the imports
    import React, {useState} from 'react';

+ Hooks can be called only inside the functions
+ When useState is called, the component in which the useState is located is updated
    const [title, setTitle] = useState(props.title);

        - 'setTitle' is the name of the function we will use to change the state
        - 'title' is the name of the variable we will put this in a curly brace in our  return block
        - props.title is the initial value of the variable 'title'

        
## props in react
+ You add the data to your app.js
+ you set the attributes of your custom component dynamically to your data using dot notation or you can hardcode the values. This is done in your app.js within the self-closing tag of your custom component.
+ In your custom component, you should then receive all the data via an argument 'props' 
+ Then you can access the value in your custom component between any tag using props.name where name is the name you used to save the value in your app.js file.
+ Props can only be passed from parent to child, we can't skip intermediate components.

## Event listeners
+ Define a function before the return block in your code.
+ <button onClick={FunctionName}>Change Title</button>
+ Do not execute the function by add (), just write the name.
+ If you add the (), javascript will automatically execute the function when the component is returned which is not what we want.

## Adding forms
+ When you use an event listner like onChange, you get an event object from the browser which contains details of the event that occur.
+ You can have access to this via an argument 'event' that youn should pass into your event handler function.
+ To get the value in an input field, you use the event.target.value
+ event.target.value will always return a string even if it is a number

## forms submission
+ We can prevent the default form submission behavior that occurs when a 'submit' button is clicked.
+ The default behaviour is that the page reloads.
+ To prevent this behaviour, we pass in the 'event' as argument and call event.preventDefault() in the body of the submit handler 
+ We can get all the data inputted from the variable name of the useState expression and add everything in an object in the submitHandler function.

## Multiple states
+ You can have multiple state
+ States are being replaced when they are updated
+ When you are updating a state that depends on another state, pass a callback that accept the previous state and then set the new state.

## Two-way binding
+ As we are updating the state in a field, we also want to pass back the new value into the input fields.
+ We do this by setting the value property in the input field to the variable name of the setState. e.g <input value={enteredDate} />
+ To clear the fields after a form submission, we set the states of the fields to an empty string in the submit handler after submission.

## Child-to-parent communication
+ We can create our own event props, give it a function as value. That will allow us to pass a function from a parent component to a child component and then call the function from the child component. When we call the function, we can pass data to the function as parameter. That is how we communicate up.
+ Props can only be passed from parent to child, we can't skip intermediate component.

## Lifting state up
+ We move data from a child component to the parent component so that we can also use the data in other children components that are related to that parent.

## Stateful and stateless/Controlled/uncontrolled components
+ A stateless component is a component that does not manage any state
+ Presentational or dumb component is a stateless component

## Adding keys to list
+ For every object or list, you should set a key which should be unique to  

## CSS Styling in react
+ You can use Styled component library or use css modules or the normal css

## React rules/errors
+ Adjacent elements must be wrapped in a single element before they are returned. That is because the returned statement is calling React.createElement()
+ undefined error means you are trying to use something (variable, function) you did not define.
+ Learn to check the console for errors
+ You can also use breakpoints to find errors
+ You can also download chrome react dev tool extension 

## React fragments
+ <React.fragment></React.fragment>
+ or <></>
+ The first syntax will always work but the second depends on your project setup.
+ you can import fragments and use the syntax below <Fragment></Fragment>

## React portals
+ It helps us to port a component to a new location nomatter how deeply nested they are in our project.
+ You can define a div in the index.html with  an id. That is where we want to render our portal
+ Import ReactDOM from react
+ call the ReactDOM.createPortal() 
+ The first argument for ReactDOM.createPortal() is the component we want to render and the second argument is where we want to render it. 
+ When you specify the coponent to render, you also have to forward the props by specifying them.

## React refs
+ It is a react hook
+ It means references
+ They allow us to get access to other DOM element and interract with them
+ You can connect your html element to any of your references.
+ When you establish the connection, the DOM node is stored as an object in the variable of the ref.
+ Rarely use ref to manipulate DOM
+ refs is good if you just need to read values and you are not managing any state.

## Controlled and uncontrolled components
+ When a form/input is being managed by the use of state and the values are being fed back into the input fields via the state management, it is a controlled component.
+ A form/input is uncintrolled if it is not being controlled by react via state or other means.

## React Effect or Side Effect
+ They are the other things you do aside rendering the UI and reacting to user input.
+ They include: 
    - Storing of data in browser storage
    - Sending of http requests to backend servers
    - Setting and managing timers

+ These are tasks that must happen outside of the normal component evaluation and render cycle - especially since they might block/delay rendering e.g (http requests) 
+ The useEffect hook is used to manage sideEffects 

## How to use  useEffect
+ It takes two arguments
    - The first is a function that should be executed after component evaluation if the specified dependencies changed.
    - The second is the dependency array
    -You must add all "things" you use in your effect function if those "things" could change because your component (or some parent component) re-rendered. That's why variables or state defined in component functions, props or functions defined in component functions have to be added as dependencies!

## How to use  useReducer
+ It is useful for more complex state e.g multiple states that change together or similar
+ It is more powerful state management
+ Syntax:
    const[state, dispatchfxn] = useReducer(reducerFxn, initialState, initFn)

    - state is the latest state

## useReducer vs useState
+ use useReducer when useState becomes cumbersome
+ use  useSate for independent piece of state/data
+ use useReducer when you have related piece of states 