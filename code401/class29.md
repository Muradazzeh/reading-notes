# react hook - useReducer 

* useReducer is usually preferable to useState when you have complex state logic that involves multiple sub-values or when the next state depends on the previous one. useReducer also lets you optimize performance for components that trigger deep updates because you can pass dispatch down instead of callbacks.

```
const initialState = {count: 0};

function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```

* useReducer
const [state, dispatch] = useReducer(reducer, initialArg, init);

## Lazy initialization
You can also create the initial state lazily. To do this, you can pass an init function as the third argument. The initial state will be set to init(initialArg).

```
function reducer(state, action) {
  switch (action.type) {
    case 'increment':
      return {count: state.count + 1};
    case 'decrement':
      return {count: state.count - 1};
    case 'reset':
      return init(action.payload);
    default:
      throw new Error();
  }
}

function Counter({initialCount}) {
  const [state, dispatch] = useReducer(reducer, initialCount, init);
  return (
    <>
      Count: {state.count}
      <button
        onClick={() => dispatch({type: 'reset', payload: initialCount})}>
        Reset
      </button>
      <button onClick={() => dispatch({type: 'decrement'})}>-</button>
      <button onClick={() => dispatch({type: 'increment'})}>+</button>
    </>
  );
}
```
## useState vs. useReducer
* useState is a basic Hook for managing simple state transformation, and useReducer is an additional Hook for managing more complex state logic. However, it’s worth noting that useState uses useReducer internally, implying that you could use useReducer for everything you can do with useState.

* However, there are some major differences between these two Hooks. With useReducer, you can avoid passing down callbacks through different levels of your component. Instead, useReducer allows you to pass a provided dispatch function, which in turn will improve performance for components that trigger deep updates.

* However, this does not imply that the useState updater function is newly called on each render. When you have a complex logic to update state, you simply won’t use the setter directly to update state. Instead, you’ll write a complex function, which in turn would call the setter with updated state.

* Therefore, it’s recommended to use useReducer, which returns a dispatch method that doesn’t change between re-renders, and you can have the manipulation logic in the reducers.

* It’s also worth noting that with useState, the state updater function is invoked to update state, but with useReducer, the dispatch function is invoked instead, and an action with at least a type is passed to it.

## When to use the useReducer Hook
As your application grows in size, you’ll most likely deal with more complex state transitions, at which point you’ll be better off using useReducer.

useReducer provides more predictable state transitions than useState, which becomes more important when state changes become so complex that you want to have one place to manage state, like the render function.

A good rule of thumb is that when you move past managing primitive data, i.e., a string, integer, or Boolean, and instead must manage a complex object, like with arrays and additional primitives, you’re likely better off with useReducer.
