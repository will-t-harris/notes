`<_>` syntax essentially means "please infer this type, rust compiler"

I used it to quickly debug the contents of an iterator like this:

```rust
dbg!(iterator.collect::<Vec<_>>());
```

Note that the contents of the iterator must implement [Debug](https://doc.rust-lang.org/core/fmt/macro.Debug.html)

[Relavant SO](https://stackoverflow.com/questions/34363984/what-is-vec)