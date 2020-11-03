Sets up husky and prettier with a pre-commit hook.

## Install
`yarn add -D prettier pretty-quick husky`

## package.json script
`"husky": {
  "hooks": {
    "pre-commit": "pretty-quick --staged"
  }
}`