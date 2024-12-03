
### Custom Componants in ReactJS
    Custom Componants in react are reusable elements that are only called when they are updated 
        Custom Componants help with modularity and breaking down larger projects into smaller peices

        Here is a Custom componant you could use as a footer

        ```javascript
        import React from "react";

        function Footer() {
        return (
            <footer>
            <p>My Website</p>
            <p>
                <a href="mailto:contact@mywebsite.com">Email Us</a> | 
                <a href="tel:123-456-7890">Contact</a>
                <a href="linkdin.com">Linkdin</a>
                <a href="Handshake.com">Handshake</a>
            </p>
            </footer>
        );
        }

        export default Footer;

        ```

### React Props
    React properties allow for data to be passed from a parent componant to a chile componant
    These are significant becuase it allows companants to communicate with eachother and allows for dynamic rendering based on the data pased form the parent to the child
    React Props are read only which means that the child element cannot change the parent element 

    Here are an example of a parent and child componant where the parent passes data to the child
# Parent Componant 
    ```javascript 
        import React from "react";
        import UserProfile from "./UserProfile";

        function App() {
        return (
            <div>
            <h1>User Profiles</h1>
            <UserProfile name="Jane Doe" age={20} email="janedoe@gmail.com" />
            <UserProfile name="John Doe" age={25} email="johndoe@gmail.com" />
            </div>
        );
        }

        export default App;

    
    ```
# Child Componant

```js
        import React from "react";

        function UserProfile(props) {
        return (
            <div>
            <h2>{props.name}</h2>
            <p>Age: {props.age}</p>
            <p>Email: {props.email}</p>
            </div>
        );
        }

        export default UserProfile;


```


### React State Management Using React Hooks 
## useState
The useState hook allows for variables to be updated while allowing the UI to continue function

useState takes an inital value and returns two elements in an array

```js
const [state, setState] = useState(initialValue);
```

state variable - The state variable is the inital/current value of the componant

setState function - the setState function calls the updated state


### useEffect
The useEffect hook is used to manage effects of functional componants 

Events like fetching data, interacting with APIs and updating the DOM are manages by useEffect

useEffect is dependent on an array value to determine when it will run

# Running only after the inital render

```js
useEffect(() => {
  console.log('Effect runs only after inital render');
}, []);

```

# Running only after the listed dependacie changes

```js
useEffect(() => {
  console.log('Effect runs when "dependant" changes');
}, [dependant]);

```

# Running after every render

```js 
useEffect(() => {
  console.log('Effect runs after every render');
});

```