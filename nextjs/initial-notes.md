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
	- Wrap this around an anchor tag. The anchor tag will take any className, etc attributes. I think the anchor tag also acts as a fallback if there's no JS for whatever reason.
```jsx
	<Link href="/cats">
		<a>Link to a cats page</a>
	</Link>
```

## Assets / Metadata

- `next` serves static files from the `public/` directory at the project root
	- this directory is also where files like `robots.txt`, Google Site Verification and other static assets should live
- `next/head` is a built in implementation for including metadata on pages (link tags, meta tags, title tags, etc)
- To modify the `<html>` tag, do so through the `pages/_document.js` file
	- https://nextjs.org/docs/advanced-features/custom-document

## CSS

- Comes with support for CSS modules and `styled-jsx` by default
- 