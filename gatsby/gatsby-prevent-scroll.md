Set  `document.documentElement.style.overflow = 'hidden'` and to enable scroll again (after modal close, for example) set `document.documentElement.style.overflow = 'visible'`.

I think that this is because `document.body` is set to scroll by default by Gatsby, so we have to target the document root instead (the `html` element)

Discovered this solution in [this](https://github.com/willmcpo/body-scroll-lock/issues/154) issue in the `body-scroll-lock` package.