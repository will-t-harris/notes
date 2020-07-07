The pattern describes using a nested function to change state based off the previous state.

This ensures that the state changes we're dealing with never get out of sync. I believe it is because of JS closures.

```jsx
<button onClick={() => setDarkMode(prevMode => !prevMode)}>
```

https://redux.js.org/recipes/structuring-reducers/immutable-update-patterns/
