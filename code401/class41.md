# Interview questions 

 **LifeCycle of React Component**

 
As we discussed already, Class Components are stateful which used several Lifecycle methods and Functional components are Stateless, In the previous story, we used React Hook method useEffect to make it stateful.

The React LifeCycle is mainly classified into three stages Mounting, Updating, UnMounting. All Class level components will go through these methods of the stages, and you can override the methods in your component to run code at the required place in the process.


LifeCycle of React Component

React Lifecycle Stages
Mounting Code Pen
Mounting is the first stage in which our React Component is created and inserted into the DOM.


Methods in Mounting
constructor()
Constructor is the first method that gets called before the component mounted which helps to initialize the component State. Whenever the class component is getting initialized the call will happen. Click here to know more about the ‘this’ keyword.


static getDerivedStateFromProps() Code Pen
getDerivedStateFromProps is a static method that gets called before the render method but, after the constructor call of the component.

It is required in this case, whenever there are props passed from the parent component that changes the state of the child component. This method is new in React lifecycle method, as of React 17 onwards introduced to replace the componentWillReceiveProps

In the example below, the render method of the parent Component as AppContent is called the child Component as Rectangle with props.



In the child Component, the State will get initialized inside the constructor, then the Life cycle method getDerivedStateFromProps will get called, the syntax of the method has two arguments, the first argument as props which we received from the parent class and the second argument as current State. Now Updating the states using the received props from the parent and then the render method will get called. Now see the order of the output


Output of getDerivedStateFromProps Method
render ()
In the above method we called, the render method will call next to getDerivedStateFromProps. We already saw more about these render calls. So, let’s go to the next method of Mounting.

componentDIDMount() Code Pen
This method gets called whenever the component gets mounted on the DOM which means the render method is completed, and it will call once in a lifecycle. Once initial rendering is done, we can make API calls and update the state with the API response. In such cases, it will be mainly helpful.

Even in the last story, we did the same in stateless components using React Hook method useEffect. As mentioned there, we are converting the same example using the class component.

API information
Sign Up and get your free API key from here

In the below example, the render method is getting called only once to render the AppContent component, during the time the State-related information getting rendered with default data.


Once it’s initially rendered, the componentDidMount method of the Lifecycle gets called and triggers a weather API to get the real-time data. Inside this method, we have setInterval time method which triggers an API call at every second interval to update the state with the API response data. As we know already, whenever the state changes, the component gets re-rendered.


The output of componentDIDMount Method
Updating
Whenever there is a change to props or state it enters into the stage Updating.


Methods in Updating
static getDerivedStateFromProps()
getDerivedStateFromProps is a static method that gets called before the render method and this is the first lifecycle method to be invoked in the updating phase. We already discussed this detail in a mounting stage which means this method gets called in both the mounting and Updating stage. So, let’s move on to the next method of Mounting.

shouldComponentUpdate() Code Pen
The shouldComponentUpdate method in the Lifecycle gets called next to getDerivedStateFromProps. As we already discussed, the component will get re-rendered whenever there is a state or props changes. If you want to control the behavior of re-render, then this method helps.


shouldComponentUpdate
In the example below, the parent component passing props of length and breadth to the child component.


Let’s see below how the child component behaves during the initial rendering.
We already know the lifecycle call hierarchy during initial rendering. The below class getting the length and breadth from the parent props and update the State in the child in the method getDerivedStateFromProps. Only the State value and props value gets differed or the State, not a default value in such cases the state to be updated.


Updating When we click the button to update the length, the call starts from updateLength method, making, making the change in State. As we know, When the state changes automatically the component re-render will happen. Before that its executes the Lifecycle methods as getDerivedStateFromProps() & shouldComponentUpdate



Output order of shouldComponentUpdate
render ()
In the above method we called, the render method will call next to shouldComponentUpdate. In render, we can only read the State not to set State. We already saw more about these render calls. So, let’s go to the next method of Updating.

getSnapshotBeforeUpdate() Code Pen
The getSnapshotBeforeUpdate method stores the previous values of the state after the DOM is updated which means once the render method is completed and before the componentDidMount.


When this method is really required? = After render before commit


In the given example creating a new row on every button click, When the rows are getting more, then we have to scroll the window to see the newly updated rows. In such kind of cases, the method helps.

Here the number of rows should not exceed the display box, if it exceeds then we have to adjust the scroll position to view the last updated row. If you connect this with real time example as chat messages, it automatically adjusts the scroll position and always shows the last message.

As we know, componentDidUpdate will start after the render method in updating. In this case the update is required to change the Scroll position. So, the getSnapshotBeforeUpdate help here to find the scroll position after the component rendered and finally the componentDidMount will update the scroll position in the DOM.

componentDIDUpdate()
We already saw more about these componentDIDMount calls in the mounting section which is invoked immediately after a component is mounted. Similarly, componentDIDUpdate calls in the updating stage which is invoked immediately after a component is updated. This method is not called for the initial render.


UnMounting

componentWillUnmount()
componentWillUnmount method is called when a component is being removed from the DOM. It is mainly used to perform cleanups that should be done for canceling network requests or canceling any subscriptions made in componentDidMount.
