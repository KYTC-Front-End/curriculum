# Context API

## What is react Context API?

React's context allows you to share data with any component, by storing this data in a central place, you can think of it as a global store where every component would be able to access it. instead of the normal way of passing the data from the parent to the direct child via props which would cause sometimes something called prop drilling.

## What is prop drilling?

Prop drilling (also called "threading"): passing props from component to another to another and so on.... refers to the process you have to go through to get data to parts of the React Component tree

- for example, if we have this tree of components

  ![](https://i.imgur.com/TGDgI2f.png)

  and if we wanted to pass data to Component `C` then we have to pass it through `A` then `B` Component before getting access to it inside the `C` component.
  we can solve this problem using **_Context API_**.

## What do we need to start working with the Context API?

It's a built-in feature.You will only need React 16.3 or above, no external libraries or anything.

## The building blocks of Context API

1. Context Instance.
2. Provider.
3. Consumer.

### Context Instance:

It is the instance we are going to use to link the parts together.

```jsx
const Context = React.createContext(defaultValue);
```

Here we are creating an instance that can receive an optional default value it is like a fallback value.
We will use this object to create the provider and the consumer

### Provider

This is the delivery system for our store, the piece that is going to deliver the data to other consumers on the app.

> we can have nested provider

```jsx
// Context is the instance the we created before
<Context.Provider value={/* some value */}>
  {/*...components that can consume the store*/}
</Context.Provider>
```

**Note:** we can't use anything other than the value prop name (it is a reserved word for the provider)

We simply say that anything wrapped under this Provider component will have access to this value via the Consumer

if the provider has a value then the consumer will use this value instead of the default value

### Consumer using useContext Hook

It is the object that we use to access the context's value.

> we can have multiple consumers subscribed to the same Provider.
> The Consumer will find the closest provider to get the data from or it will use the default value if the Provider value was omitted.

The value we pass to the Provider is sent to our Consumer as a param to the Consumer function

```jsx
const consumer = React.useContext(ContextObj)
...
//you can now access consumer values using consumer variable

```

## Exercise

Let's use the Context API with our app

We will use a simple example for the sake of simplicity, but you can imagine this part being a part of a bigger app.

This is the tree of our app:
App->MoviesListPage->MoviesListComp->Card

> of course this is a simple example but with a real application, we will have more nested components, think of the times that you needed to pass you user's info to multiple layers before reaching the component you want

1. Clone the repo, install the dependencies, run the app, check the files and the components.
2. Now let's create our Context:

   - Create a folder called `context` on the src folder.
   - Create a file called `MoviesContext.js`.
   - Now let's create our Context instance.

<details><summary>Code</summary>

```jsx
import React from "react";

const MoviesContext = React.createContext();

export default MoviesContext;
```

</details>

3. Import the context instance inside the app component and wrap what inside the app with the Context.Provider and pass the movies and the delete function to Provider value property.

<details><summary>Code</summary>

```jsx
import MoviesContext from './context/moviesContext';
//....code

render() {
    return (
      <MoviesContext.Provider value={{ deleteMovie, movies }}>
        <div className="App">
          {/* <Nav /> */}
          <h1>MOVIES</h1>
          <MoviesListPage />
          {/* other components that can use the same data that why we needed to left the state up */}
          {/* <UserPage movies={this.state.movies} /> */}
        </div>
      </MoviesContext.Provider >
    );
  }

```

</details>

4. Now all we have to do is to use this data on any component descendant of the same vertical line
   - Import the context instance from MoviesListComp.
   - Call `useContext` Hook with context object as the argument.

<details><summary>Code</summary>

```jsx
import MoviesContext from "./context/moviesContext";
//....code

const MoviesListComp = () => {
  const { movies, deleteMovie } = React.useContext(MoviesContext);

  return <ul>{movies.map((movie) => createCard(movie, deleteMovie))}</ul>;
};
```

</details>

5. Everything is done this how we can use the Context API

---

## Refactor to a central store

We can refactor our code to have **a central store**.

1. Now on our moviesContext file create a component called MoviesProvider or any name you want.
2. Move the state and the deleteMovie method from the App to MoviesProvider component.
3. We will receive the other components using children props.

<details><summary>Code</summary>

```jsx
import React from 'react';

export const MoviesContext = React.createContext();

function MoviesProvider ({children}) {
  const [movies, setMovies] = React.useState(moviesList);

  deleteMovie = (id) => {...}

  render() {
    return (
      <MoviesContext.Provider value={{ deleteMovie, movies }}>
        {children}
      </MoviesContext.Provider>
    );
  }
}

export default MoviesProvider;

```

</details>

4. And the last step is to wrap the App component with the MoviesProvider instead of the Context.Provider.

<details><summary>Code</summary>

```jsx
import MoviesProvider from "./context/moviesContext";

const App = () => {
  return (
    <MoviesProvider>
      <div className="App">
        {/* <Nav /> */}
        <h1>MOVIES</h1>
        <MoviesListPage />
        {/* other components that can use the same data that why we needed to left the state up */}
        {/* <UserPage movies={this.state.movies} /> */}
      </div>
    </MoviesProvider>
  );
};

export default App;
```

</details>

## Final notes

- Context have a third property called displayName which used to give a name to the Provider on react-dev-tool, imagine you have multiple provider then it will be hard to tell which one is which without clicking it.

![](https://i.imgur.com/iRkIS2Z.png)

```jsx
export const MoviesContext = React.createContext();
MoviesContext.displayName = "MoviesContext";
```

after this the Provider will have a name.

![](https://i.imgur.com/N2SeNYa.png)

- You can Consume Multiple Contexts.
- All consumers that are descendants of a Provider will re-render whenever the Provider’s `value` prop changes.
- [Performance tips](https://reactjs.org/docs/context.html#caveats).
- You should not always use the context if you only passing the data down two or three components.
- Get back to [this](https://github.com/facebook/react/issues/15156#issuecomment-474590693) after you are comfortable with the Context API and the Hooks.

- ### Redux vs Context API:

  **_It is up to you but these are some of the things to keep in your mind before deciding on using one over the other_**

  **Context API**

  - Context is hard to debug doesn't have debugging tools like redux.
  - No middlewares with Context API.

  **When to use Redux:**

  - Separation of concern(every function pure and do one thing/ you know everything about the input and the output)
  - Predictability(you know everything about the state/action shape...)
  - Ease of test (pure function)
  - Community support
  - Redux devtools(time travel)
  - MiddleWares

  **When not to use Redux:**

  - 10 components for example
  - Large application but only a few components interact with each other
  - The size of the application where the bundle became bigger with redux
