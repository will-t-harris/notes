Here, we will be using [pug](https://pugjs.org/api/getting-started.html) as our templating engine. Was formerly known as Jade.
- pug is indentation-based
- pug uses what emmet-style shortcuts for classes and ids
- [other attributes documentation](https://pugjs.org/language/attributes.html)
- pug uses `#{}` to interpolate values inside the template inside of text
	- use template literl interpolation to bring values into string literals
- you can run JS inside of pug files, following a `-` or within an interpolated value
	
- `views` folder is where all of our `.pug` templates will live
	- in our express app file, we declare where our views are with:
	 ```js
	app.set("views", path.join(__dirname, "views"))
	```
	- [the `path` module is native to node](https://nodejs.org/api/path.html#path_path) and is used for working with file and directory paths
	- we declare our view/templating engine with:
	```js
	app.set('view engine', 'pug')
	```

- [We use `res.render()` to render out a template](https://expressjs.com/en/4x/api.html#res.render). It takes two things:
	1. The template to render
	2. Locals object

- To get data from our route to our template, we pass it in via the locals object
	- here our template is `hello.pug`
	- the cat value is coming from the query
```js
router.get('/', (req, res) => {
	res.render('hello', {
		name: "Test Name",
		cat: req.query.cat
	})
})
```

- we can set up a base layout template, representing the html document defaults, that can then be shadowed with other values (?)
	- to use the layout (or other) templates, we use `extends layout` at the top of the pug file
- we can use template **blocks** to essentially create template components that can be passed around




























