Assumes that gatsby cli is installed (I used 2.10.4)
1. `yarn add gatsby-plugin-mdx @mdx-js/mdx @mdx-js/react twin.macro @emotion/core @emotion/styled gatsby-plugin-emotion`
2. Add `gatsby-plugin-mdx` and `gatsby-plugin-emotion` to plugins array in config
3. In `gatsby-browser`:
```js
import 'tailwindcss/dist/base.min.css'
```
4. Add `gatsby-plugin-layout`, `gatsby-plugin-page-creator` and include in config plugins
5. Move layout file to `/src/layouts/index.js` (this is the default that `gatsby-plugin-layout` looks for)
6. Run `npx tailwind init` on command line
