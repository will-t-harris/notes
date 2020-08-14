## Installation
- `npm i -g @vue/cli` to install vue-cli globally
- `@vue/cli-service-global` is the server package
- `vue build` builds app in production

## Directives
- `<directive>: <attribute>=<value>`
- prefixed with `v-`, indicates that they are special attributes provided by Vue
	- `v-bind`
		- bind a value to an attribute in the DOM
		- `key` binding required for list items
	- `v-once`
		- perform one-time interpolation, will not be affected by data changes
		- also affects other bindings on same node
	- `v-if`
		- conditional on a value
	- `v-for`
		- loop over things
	- `v-on`
		- attach event listeners
	- `v-model`
		- creates a two-way binding
	- `v-html`
		- interprets html syntax as plain html
		- this is definitely vulnerable to XSS, careful with `v-html` interpolation

## Errata

- Single components as default export per `.vue` file
- Bi directional data -- bind stuff
- All Vue components are also Vue instances, and accept an options object
- When instantiating state, start out with an empty value or view updates will not trigger on that value
- `{{}}` syntax for interpolation interprets data as plain text