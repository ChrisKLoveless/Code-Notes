# React with NoSQL Notes

### Hooks
[React Docs on Hooks](https://reactjs.org/docs/hooks-intro.html)

* Hooks are functions that let you “hook into” React state and lifecycle features from function components. Hooks don’t work inside classes — they let you use React without classes.
  * useState()
  * useEffect
    * We should use the useEffect hook when we want to run code in any of the following cases:
    * After our component is first rendered. This corresponds to the componentDidMount lifecycle method.
    * When a state variable in our component changes. This corresponds to looking at the prevState variable available in the componentDidUpdate lifecycle method to determine if state has changed, and to only make an update if it has.
    * After every re-render of our component. This corresponds to the componentDidUpdate lifecycle method.
    * `Dependency Arrays` are passed into useEffect hooks to order to only initialize effect if the state changes. An empty array means it should only run once after the first render.


* Rules for Hooks
  1. Only call hooks at the top level of a function component. Don’t call hooks inside loops, conditions, or nested functions.
  2. Only call hooks from React function components. Don’t call hooks from regular JavaScript functions (unless you are creating a custom hook — more on this soon!) or class components.

* Best Practices for Hooks
  1. Use multiple hooks to handle different concerns.
    * For example, it's better to use multiple useState hooks to handle different state variables, instead of grouping them into one useState hook.
    * You should also use multiple useEffect hooks to manage different effects. Doing so practices separation of concerns and is a huge benefit with the useEffect hook.
  2. Convention dictates that the name of custom hooks should start with "use", like useState or useTimer. Later in this lesson, we'll create a custom hook called useTimer!
    * Take note that the ESLint plugin for React hooks relies on this naming convention to identify hooks and any issues with them.

### Firebase, Firestore, and NoSQL

* [Documentation Guide](https://www.learnhowtoprogram.com/react/react-with-nosql/firebase-documentation)

* [Setting up a Firebase project](https://www.learnhowtoprogram.com/react/react-with-nosql/setting-up-a-firebase-project-firestore-database-and-web-app)

* `Firebase` is a cloud-based NoSQL database solution offered by Google. It is cloud based and real-time. Cloud based means it exists online. Real-time means we can see database changes immediately.
* `Firestore` is also a cloud based BaaS and make it easier to query our database. Be sure to follow links on making rules more secure if planning to deploy project.