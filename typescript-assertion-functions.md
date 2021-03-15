TypeScript versions 3.7+ allow assertion functions to narrow types

The `asserts condition` bit is the new syntax that causes the compiler to narrow the types

A bang before `condition` is not syntactically valid

## General assertion on given condition

Throws an error unless given condition is true

```
function assert(condition: boolean): asserts condition {
  if (!condition) {
    throw new Error('Assertion failed');
  }
}
```

## Assertion on a specific type

Rather than type guard syntax (`n is number`), this allows us to type narrow to a specific type

```
function assertNumber(n: unknown): asserts n is number {
  if (typeof n !== 'number') {
    throw new Error("Value wasn't a number: " + n);
  }
}
```

## Difference when compared with type guards

While type guards and assertion functions can both narrow types, type guards only narrow types for the block in which they have scope. Assertion functions narrow types for all code that follows after the assertion function.

Just like with type guards, the compiler can't check that our logic is correct. This would compile, even though it contains a logical error.

```
function assertNumber(n: unknown): asserts n is number {
  if (typeof n !== 'string') {
    throw new Error("Value wasn't a number: " + n);
  }
}
const s: string = 'a string';
assertNumber(s);
const n: number = s;
n;

// 'a string'
```

Because of this, type guards and assertion functions should have automated tests that verify they work as expected.