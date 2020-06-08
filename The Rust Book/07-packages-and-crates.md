## Crates
- A crate is a binary or library
- All funcitonality of a crate is accessible via the crate's name
	- This enables bringing a crate's functionality into scope anywhere that its needed
- A package can have multiple binary crates
	- they live in `src/bin`
	- each file in `src/bin` will be a separate binary crate
- The *crate root* is the source file that the Rust compiler starts from
	- It makes up the root module of a crate
	-  `src/main.rs` is conventionally the crate root of a binary crate
	-  `src/lib.rs` is conventionally the crate root of a library crate
	-  Cargo passes the crate root files to `rustc` to build the library or binary
		-  `rustc` is the Rust compiler

## Packages
- A package is one or more crates that provide a set of functionality
- Packages contain:
	-  a `Cargo.toml` that describes how to build the crates in the package
	- it *must* contain zero or one library crates
	- it can contain many binary crates 

## [Defining Modules to Control Scope and Privacy](https://doc.rust-lang.org/book/ch07-02-defining-modules-to-control-scope-and-privacy.html#defining-modules-to-control-scope-and-privacy) 

### Modules

 - Modules are organizational, allowing for greater readability and easy reuse
 - Modules control the privacy of items (public or private)
 - Defined with `mod` keyword followed by the module name
 ```rust
 mod front_of_house {
 	// Code
 }
 ```
 - Modules can also contain other modules, structs, enums, functions, traits, constants
 ```rust
 mod front_of_house {
 	mod hosting {
		// Code
	}
	
	mod serving {
		// Code
	}
 }
 ```
 - Modules are organized in a tree-like structure, similar to a filesystem
	 - Have parent/child/sibling relationships
 
crate
  └── front_of_house
    ├── hosting
    │   ├── add_to_waitlist
    │   └── seat_at_table
    └── serving
         ├── take_order
         ├── serve_order
         └── take_payment
