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

### Actions 
Actions are objects that describe something that happened. They're `dispatched` to the Redux store and handled by `reducers`. The reducer receives the action and executes logic based on the action's `type` that alters state. Data included with the action is called a payload. `Actions are the only way to invoke state updates in Redux.`

### PubSub pattern
Objects can publish updates to the store and dependents can subscribe to changes.

### Bindings
`Bindings` are libraries that help two languages, tools, or technologies integrate with one another. They usually do this by "wrapping" logic and functionality from one technology into functions that are easier to call in the second technology.

### Higher-order Components
This is a common term in React. A higher-order component is a function that takes an existing component, wraps it with additional functionality, and then returns it so it can be used elsewhere in an application. `connect()` is an example.
