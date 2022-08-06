# Component Based UI - React- 

The smallest React example looks like this:
```
const root = ReactDOM.createRoot(document.getElementById('root'));
root.render(<h1>Hello, world!</h1>);

```
## What are the building blocks of a React app?

* Elements.
* Components.
## What is the difference between Element and Component ?

* React Element: It is the basic building block in a react application, it is an object representation of a virtual DOM node. React Element contains both type and property. It may contain other Elements in its props. React Element does not have any methods, making it light and faster to render than components.

```
npm create-react-app project
```


## What are some advantages of React’s component based architecture?
 * Reusability: In Component Driven Development, the development process is in place, components once created can be easily used across as many modules as needed
 * Repetition: An application is often an interface made up of repeating components. Repetition in component developments provides developers to maintain and scale their code on large. Repetition provides familiarity which makes the user feel the symmetric design and helps them to make informed decisions.
* Scalability: Component Driven Development allows for extending the benefits of a modular architecture to the frontend as well.
* Simpler maintenance: Component Driven Development models in software engineering keep you away from such unwanted situations. 
* Faster development: Component Driven Development reduces development time a lot, furthermore the relationship with the codebase.


## What is JSX and why do we use it?
* stands for JavaScript XML. JSX allows us to write HTML in React. JSX makes it easier to write and add HTML in React

* at it is totally safe to embed user input via JSX




# Rendering Elements
* Rendering is a term that can be understood on different levels of abstraction. Depending on the context, it has a slightly different meaning. In any case, ultimately, it describes the process of generating an image.


* Components defined as classes currently provide more features which are described in detail on this page. To define a React component class, you need to extend React.Component:
````
class Welcome extends React.Component {
  render() {
    return <h1>Hello, {this.props.name}</h1>;
  }
}
````
* React Only Updates What’s Necessary
React DOM compares the element and its children to the previous one, and only applies the DOM updates necessary to bring the DOM to the desired state
