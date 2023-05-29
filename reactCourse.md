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

## Event listeners
+ Define a function before the return block in your code.
+ <button onClick={FunctionName}>Change Title</button>
+ Do not execute the function by add (), just write the name.
+ If you add the (), javascript will automatically execute the function when the component is returned which is not what we want.

## Adding forms
+ When you use an event listner like onChange, you get an event object from the browser which contains details of the event that occur.
+ You can have access to this via an argument 'event' that youn should pass into your event handler function.
+ To get the value in an input field, you use the event.target.value