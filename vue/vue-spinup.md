## Installation
- `npm i -g @vue/cli` to install vue-cli globally
- `npm i -g @vue/cli@next` installs v3 (beta)
- `@vue/cli-service-global` is the server package
- `vue build` builds app in production

## Directives
- `<directive>: <attribute>=<value>`
- prefixed with `v-`, indicates that they are special attributes provided by Vue
	- `v-bind`
		- bind a value to an attribute in the DOM
		- `key` binding required for list items
		### `v-bind` shorthand
		- `v-bind:href=` === full syntax
		- `:href=` === shorthand
		- `:[key]=` === shorthand with dynamic arg
	- `v-once`
		- perform one-time interpolation, will not be affected by data changes
		- also affects other bindings on same node
	- `v-if`
		- conditional on a value
		- example of `v-if="seen"`
			- if `seen === true` the thing will be visible
			- if `seen === false` the thing will not be visible
			- can use conditionals like this to control element presence
	- `v-for`
		- loop over things
	- `v-on`
		- attach event listeners
		- `v-on:click="doSomething"`
		### `v-on` shorthand
		- `v-on:click=` === full syntax
		- `@click=` === shorthand
		- `@[event]=` === shorhand with dynamic arg
	- `v-model`
		- creates a two-way binding
		- use this to bind the value of an input to another element, for example
	- `v-html`
		- interprets html syntax as plain html
		- this is definitely vulnerable to XSS, careful with `v-html` interpolation

## Modifiers

- special postfixes denoted by a dot that indicate that a [[vue-spinup#Directives]] should be bound in some special way
- `.prevent` tells `v-on` to call `event.preventDefault()`, for example

## Errata

- Single components as default export per `.vue` file
- Bi directional data -- bind stuff
- All Vue components are also Vue instances, and accept an options object
- When instantiating state, start out with an empty value or view updates will not trigger on that value
- `{{}}` syntax for interpolation interprets data as plain text
- Don't use arrow functions on an options property or callback, because arrow functions default to global scope for this