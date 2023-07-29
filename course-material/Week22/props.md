

## Props
Props are read-only components. It is an object which stores the value of attributes of a tag and work similar to the HTML attributes. It allows passing data from one component to other components. It is similar to function arguments and can be passed to the component the same way as arguments passed in a function. Props are immutable so we cannot modify the props from inside the component.  React’s data flow between components is uni-directional (from parent to child only).

Here is an example of how data can be passed by using props:

```javascript
class ParentComponent extends Component {    
    render() {    
        return (        
            <ChildComponent name="First Child" />    
        );  
    }
}

const ChildComponent = (props) => {    
    return <p>{props.name}</p>; 
};
```


## State
 unlike props, components cannot pass data with state, but they can create and manage it internally.
The state is an updatable structure that is used to contain data or information about the component and can change over time. The change in state can happen as a response to user action or system event. It is the heart of the react component which determines the behavior of the component and how it will render. A state must be kept as simple as possible. It represents the component's local state or information. It can only be accessed or modified inside the component or by the component directly.

## Difference between State and Props
![enter image description here](https://i.ibb.co/9VDFVGt/props-VSState.png)

The below table will guide you about the changing in props and state.

![enter image description here](https://i.ibb.co/qWc71Yv/Screenshot-2023-07-29-180713.png)


