## Redux Notes 

### The Three Main Rules

1. `Single Source of Truth`
In a Redux application, state must be stored as an object tree in a `store`. An object tree (also commonly referred to as a state tree) is a big object that can contain multiple slices of state (like the state slices we used in the React Fundamentals course section). And a store is exactly what it sounds like: a Redux-managed location to store application state. The store acts as the "single source of truth" for the whole app.

2. `State is Read-Only`
Redux state is strictly read-only. We cannot modify state directly. The only way to change state in Redux is to dispatch an action. The action communicates our intention to change state to the store. We won't use setState() to update state with Redux.

3. `Changes are Made with Pure Functions`
Redux requires that we make changes to state using pure functions. This makes our code easier to test and we can ensure no unintended side effects will occur.

### Stores
The Redux `store` is the single source of truth for our state and where the state resides.

### Reducers
Reducers allow us to update or mutate state in our store. They communicate the intended actions to the store.
Reducers must be pure functions to avoid any unintended side effects.
A reducer takes two arguments, the current state and action to alter the current state. It is Redux convention to capitalize actions and separate words with an underscore.
A reducer tells the store what it should handle actions.

### Actions 
Actions are objects that describe something that happened. They're `dispatched` to the Redux store and handled by `reducers`. The reducer receives the action and executes logic based on the action's `type` that alters state. Data included with the action is called a payload. `Actions are the only way to invoke state updates in Redux.`

### PubSub pattern
Objects can publish updates to the store and dependents can subscribe to changes.

### Bindings
`Bindings` are libraries that help two languages, tools, or technologies integrate with one another. They usually do this by "wrapping" logic and functionality from one technology into functions that are easier to call in the second technology.


### subscribe()
The subscribe method adds a change listener that will be called whenever an action is dispatched. Then call getState() to read the current state. Then dispatch() is used to make an action change to the store.

### React Redux Library
This library contains the official bindings for adding Redux to a React project.
`Bindings` are libraries that help two technologies to integrate with one another. Tools used: <Provider>, connect(), dispatch(), and mapStateToProps.
<Provider> will be the parent component of the app and pass it's methods down to it's children components.

### Refactoring a React app to use Redux
1. Add libraries
```JS
import { legacy_createStore as createStore} from 'redux'
```
2. Create Redux Store by importing createStore and the reducer into the index.js (webpack entry point)
3. Configure the React-Redux Provider (wrap <App /> within the <Provider> component in index.js)
4. Connect components to store. Components that need access to store will need the `connect` function.
* _Note that it's important that connect() is called right before we export the component. That ensures that the component that's exported has all necessary React Redux functionality._
5. Dispatch actions to Mutate Store State (add dispatch() to React methods that modify state)
6.  Remove state slices from store that will now be handled by Redux.
7.  Add dispatch(action) to methods 
example:
```JS
 handleAddingNewTicketToList = (newTicket) => {
    const { dispatch } = this.props;
    const { id, names, location, issue } = newTicket;
    const action = {
      type: 'ADD_TICKET',
      id: id,
      names: names,
      location: location,
      issue: issue,
    }
    dispatch(action);
    this.setState({formVisibleOnPage: false});
  }
```

### Higher-order Components
This is a common term in React. A higher-order component is a function that takes an existing component, wraps it with additional functionality, and then returns it so it can be used elsewhere in an application. `connect()` is an example.



### date-fns
Command to install and steps to set up 
```
$ npm install date-fns@2

import { formatDistanceToNow } from 'date-fns'; //where needed

formatDistanceToNow(new Date(), {   // example helper function
  addSuffix: true
});

OR

formatDistanceToNow(new Date());  //omit the suffix property
```
[docs](https://date-fns.org/docs/Getting-Started)


### Life Cycle Method
The React lifecycle is a series of methods that is always called in a certain order. We can use these lifecycle methods to call our own methods at a very specific time during a component's lifecycle. We've actually used the most common lifecycle methods before: constructor() and render(). The order of these functions matters and should be called after the constructor in a class component.



















