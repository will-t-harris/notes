## Char

- char is a [Unicode scalar value](http://www.unicode.org/glossary/#unicode_scalar_value)
	- "Any Unicode code point except high-surrogate and low-surrogate code points. In other words, the ranges of integers 0 to D7FF$_{16}$ and E000$_{16}$ to 10FFFF$_{16}$ inclusive. "
	- This includes single letters, numbers, emoji, special language characters, etc
	- Always 4 bytes in size

## Array

- Fixed-size, denoted `[T; N]`, for element of type `T` with **compile-time** constant size `N`
	- You can either initialize an array as an array literal (`[a, b, c]`) or with a repeat expression `["boop"; 100]`
	- You can also use a range to initialize an array. `0..100` would result in an array filled with numbers from 0 to 100.

## Tuple

- A collection of values of different types, constructed using parentheses `()`.
- Can hold any number of values
- Tuples can be destructured

## Struct

- Classic C-like structs use this syntax:
	- They are instantiated almost like an object literal in JS
```rust
// struct definition
struct StructName {
	field1: T,
	field2: T2,
	...
};

// struct creation
StructName {
	field1: value1,
	field2: value2,
	...
}
```
- Tuple structs use this syntax
```rust
struct TupleStruct(T1, T2, ...);
```
- Unit structs implement nothing, and are useful for generics
- Structs can also contain methods, using the `impl` keyword
- Structs have a 'spread' syntax `..` called the [struct update syntax](https://doc.rust-lang.org/stable/book/ch05-01-defining-structs.html#creating-instances-from-other-instances-with-struct-update-syntax)
	- The update syntax must be at the end of the struct	
	- Any fields that you want to overwrite come before the update

## Lifetimes

Bound to the scope within which it is created

## Iterators

Implement the `Iter` trait
Can call `next()` to hit next step in iterator
Ways of processing streams of information

Can call methods like map, reduce, etc on iterators.

Can `collect()` iterators into other data types

## Box

`std::boxed::Box`

"A smart pointer used to store data on the heap, which also allows us to wrap a recursive type"

## Arc

`std::sync::Arc`

"A thread-safe reference-counting pointer. 'Arc' stands for 'Atomically Reference Counted'"

In general, you cannot obtain a mutable reference to something inside an `Arc` because it is by definition a shared resource.

If you need to mutate, use `Mutex`, `RwLock`, or one of the `Atomic` types.

## Traits

> Traits are similar to a feature often called *interfaces* in other languages, although with some differences

Defines shared methods that all implementations of a given trait must fulfill.
Traits are an expression of shared behavior across different types.

## Threads

`use std::thread`

To create a thread call the `thread::spawn` function and pass it a closure containing the code we want to run in the new thread.