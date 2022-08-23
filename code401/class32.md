
# Context API - Behaviors
## Dream State
From an engineering standpoint, our snackbar system must easy to use and generally be very lightweight. We want to be able to place one on the screen with just a couple of lines of code. Anything more and it’s overkill.

This means forget render props and higher order components. We don’t want to deal with a messy React tree and wrappers. We don’t want action creators, reducers*, or any of that stuff.

Hooks are a perfect fit here. So lets imagine we have a custom hook that lets us do this and work backwards

```
const { addAlert } = useSnackBars()
...
addAlert('Your profile is updated!')
```

## Globally Accessible
The state of our snackbars (which ones are visible) can be localized to a single centralized component. That same centralized component can be responsible for rendering them. There’s really no need for another component somewhere in the tree to hook into that state (at least not in our use-case).

However, the management of that state (adding, removing) needs to be globally accessible.

Context can let us do just this.

## Higher Level API & Behaviour

```
export const SnackBarContext = createContext()

const AUTO_DISMISS = 5000

export function SnackBarProvider({ children }) {
  const [alerts, setAlerts] = useState([])
  
  const activeAlertIds = alerts.join(',')
  useEffect(() => {
    if (activeAlertIds.length > 0) {
      const timer = setTimeout(() => setAlerts((alerts) => alerts.slice(0, alerts.length - 1)), AUTO_DISMISS)
      return () => clearTimeout(timer)
    }
  }, [activeAlertIds])

  const addAlert = (alert) => setAlerts((alerts) => [alert, ...alerts])

  const value = { addAlert }
    
  return (
    <SnackBarContext.Provider value={value}>
      {children}
      {alerts.map((alert) => <SnackBar key={alert}>{alert}</SnackBar>)}
    </SnackBarContext.Provider>
  )
}
```
* There’s a lot more happening now. Our provider now exposes a new function called addAlert. This function uses the local state mutator useState to properly append a new alert without destroying existing ones. You could do more fancy things here: de-dup alerts, assign unique IDs to alerts so that we can also expose a removeAlert function that makes use of those IDs, and so on. But we’re going to keep it simple



## provider 
* With regard to the React Context API, what does a “provider” do?
React’s provider pattern is a powerful concept. React uses provider pattern in Context API to share data across the tree descendant nodes. You may not find this useful when you are using plain react. However, this pattern comes handy when you are designing a complex app since it solves multiple problems.

* Context provide a way to pass data through the component tree without having to pass down manually at every level

## Sprinkling in Optimizations
Our custom hook is now fully operational! We can add alerts easily from anywhere and our provider will display them for us. We could stop here, but there’s room for some optimizations that are pretty easy to achieve.

You’ll notice that value is a new object being created every single time this provider is rendered. That’s not great, because anything consuming this value from the context will potentially also be getting re-rendered.

We can use useMemo to memoize value . There’s no reason this object needs to be re-created every time. We’ll pass to it addAlert as a dependency, i.e. the memoization cache needs to be re-filled if addAlert changes.

```
const value = useMemo(() => ({ addAlert }), [addAlert])
```
