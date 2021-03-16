TypeScript automatically 'widens' types as a quality of life feature. 

For example, the type of this variable will be `boolean`, not `true`. TypeScript widens it to the `boolean` type because more often than not that's the type that we actually want.

```
let thing = true
```

To prevent this type widening, we can use the `as const` syntax

```
let thing = true as const
```

With this syntax, `thing` will be of type `true`.