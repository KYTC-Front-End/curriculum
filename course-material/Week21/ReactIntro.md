# Intro to React

> React is javascript library for building user interfaces. These interfaces are build using components (lego pieces that fit together to create complex applications). It was also created to simplify making UIs that change frequently over time, depending on user input.

## 1. Core Features of React.js

##### Source: [React docs](https://reactjs.org/), [Rithm School, Introduction to React](https://www.rithmschool.com/courses/react-fundamentals/introduction-to-react) and Oliver Phillip's (@oliverjam) [presentation on How Modern frontend fits in](https://hackmd.io/@oli/SJauYz6EM?type=slide#/).

**Component-based design:** Components are reusable pieces of Javascript logic, HTML, and CSS that are combined into one piece of an application that you can then use to build/compose a larger application. They can include inputs, properties, emit events, hold their logic and data, and also include other components.

**A Declarative API:** When you're building UIs in React, we write what we want our components to look like depending on how the user interacts and forget about how.

**JSX:** When building projects with react, we'll be using a syntax called JSX, which is basically an HTML-JavaScript hybrid. When writing with JSX, you'll effectively be able to write HTML directly inside of your JavaScript code.

**Virtual DOM**: React abstracts away from the DOM, featuring its own JavaScript representation of the actual DOM, a diffing engine which only re-renders sections it has to.

### Separation of concerns

Until now we have separated our code by file extension: HTML, CSS, and JavaScript. We flip this on its head in React and instead think about our interfaces as pieces of functionality e.g. a modal, a list, a navbar, a card. The component renders HTML-looking syntax (effectively combining JS with HTML).

## 2. Creating elements, from DOM to JSX

To illustrate the transition from using the DOM to create elements to using React and JSX syntax, we'll go through a [simple example](https://github.com/jema28/react-intro/blob/master/creating-element-dom-to-jsx/mentor-notes.md) of creating a div including two elements and rendering them to the page.
