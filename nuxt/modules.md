## Modules

"Modules are Nuxt.js extensions which can extend its core functionality and add endless integrations."

- Nuxt modules are functions that are called sequentially as Nuxt starts

## Nuxt Official Modules

- [`@nuxt/http`](https://http.nuxtjs.org/)
	- based on [`ky-universal`](https://github.com/sindresorhus/ky-universal)
- [`@nuxt/content`](https://content.nuxtjs.org/)
	- fetch files from `/content` directory in .md, JSON, YAML, CSV formats with a "MongoDB-like API"
- [`@nuxt/axios`](https://axios.nuxtjs.org/)
	- official axios integration
- [`@nuxt/pwa`](https://pwa.nuxtjs.org/)
	- official PWA solution
- [`@nuxt/auth`](https://auth.nuxtjs.org/)
	- official auth solution

## Useful Community Modules

- `@nuxtjs/tailwindcss`
	- `yarn add -D @nuxtjs/tailwindcss`
	- This doesn't *require* a `tailwind.config.js` file
	- To get vscode autocomplete, the config file is necessary
	- Add the package to the `buildModules` array in `nuxt.config.js`