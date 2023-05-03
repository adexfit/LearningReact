## Using the useEffect Hook in react
+ it performs side effect on a functional component
+ it replaces all the lifecycle functions inn the class components

+ In class components we have: 
    componentDidMount: when component mounts/loads 
    componentDidUpdate: when component prop changes 
    componentWillUnmount: When component unmounts/cleanup function 


useEffect
- The first argument is an arrow function
- The second argument is a dependency array. This is optional.
- Every single useEffect will fire once the component loads

# To run on every render
+ If the second argument is not included, the function will trigger on every render
useEffect(() => {
    console.log("I re-render") 
});


# To run on first render/mount only - componentDidMount alternative
+ If the second argument is included as an empty array
useEffect(() => {
    
}, []);

# To run on function when specified variable changes - componentDidUpdate alternative
+ If the second argument is included as an array of dependencies(variables), it will rerender when the specified variable changes
useEffect(() => {
    console.log(`The name changed: ${name}`);
}, [name]);

# To run a cleanup function - componentDidUpdate alternative
+ The function will run before the component unmount 
+ A component will unmount before it rerender
+ If the second argument is included as an array of dependencies(variables), it will rerender when the specified variable changes
useEffect(() => {
    console.log(`The name changed: ${name}`);
}, [name]);







## Using the useState Hook in react
+ state is a corect way of defining variable in react
+ We can store anything inside a state
+ we can now use state inside a functional component
+ The second argument is a setter

const [count, setCount] = useState(0);

    - count is the name of the variable
    - count will have an initial value of zero
    - setCount is the setter function 
    - state is non persistence

## Example of useState in a functional component

function App(){
    const [count, setCount] = useState(0);
    const [count, setAge] = useState(0);

    const increment = () => {
        setCount(count + 1);
    };
    const decrement = () => {
        setCount(count - 1);
    };

    return(
        <div>
            <h1>Welcome to my counter</h1>
            <p>The count is: {count}</p>
            <button onClick = {decrement}> - </button>
            <button onClick = {increment}> + </button>
        </div>
    );
}


## Example of useState in a class component
import React, { Component } from 'react'

export default class AppClass extends Component {
    render() {
        return (
            <div>
            </div>
        )
    }
}

