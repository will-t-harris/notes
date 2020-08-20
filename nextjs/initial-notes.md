## Spinup

- `npx create-next-app <project name>` initializes default next application with `react`, `react-dom`, and `next` as dependencies

## Pages / Routing

- create pages in the `pages/` directory, `next` will pick them up as site routes
- `next` picks up any exported `react` components as pages
	- the components must be default exports
	- it also seems conventional to use normal function syntax
		- you can use anonymous arrow functions for the component, but you lose the component name in the react dev tools (it becomes `<Anonymous />`)
- `next/link` exposes a `<Link />` component for internal client-side navigation
	- this component prefetches code for the linked page in the background
	- Wrap this around an anchor tag. The anchor tag will take any className, etc attributes
```jsx
	<Link href="/cats">
		<a>Link to a cats page</a>
	</Link>
```