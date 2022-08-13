# Using the Effect Hook
* The Effect Hook lets you perform side effects in function components:
```
import React, { useState, useEffect } from 'react';

function Example() {
  const [count, setCount] = useState(0);

  // Similar to componentDidMount and componentDidUpdate:
  useEffect(() => {
    // Update the document title using the browser API
    document.title = `You clicked ${count} times`;
  });

  return (
    <div>
      <p>You clicked {count} times</p>
      <button onClick={() => setCount(count + 1)}>
        Click me
      </button>
    </div>
  );
}
```
* What does useEffect do? By using this Hook, you tell React that your component needs to do something after render. React will remember the function you passed (we’ll refer to it as our “effect”), and call it later after performing the DOM updates. In this effect, we set the document title, but we could also perform data fetching or call some other imperative API.
* Use Multiple Effects to Separate Concerns
One of the problems we outlined in the Motivation for Hooks is that class lifecycle methods often contain unrelated logic, but related logic gets broken up into several methods

## Effect Cleanup
Some effects require cleanup to reduce memory leaks.

Timeouts, subscriptions, event listeners, and other effects that are no longer needed should be disposed.

We do this by including a return function at the end of the useEffect Hook.

## use Effect cases

* A) Not provided: the side-effect runs after every rendering.
````
import { useEffect } from 'react';
function MyComponent() {
  useEffect(() => {
    // Runs after EVERY rendering
  });  
}
````
* B) An empty array []: the side-effect runs once after the initial rendering.

```
import { useEffect } from 'react';
function MyComponent() {
  useEffect(() => {
    // Runs ONCE after initial rendering
  }, []);
}
```

* C) Has props or state values [prop1, prop2, ..., state1, state2]: the side-effect runs only when any dependency value changes.
```
import { useEffect, useState } from 'react';
function MyComponent({ prop }) {
  const [state, setState] = useState('');
  useEffect(() => {
    // Runs ONCE after initial rendering
    // and after every rendering ONLY IF `prop` or `state` changes
  }, [prop, state]);
}
```

