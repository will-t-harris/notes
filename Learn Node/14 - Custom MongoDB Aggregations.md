1. add routes to index file `routes/index.js`
```js
router.get('tags', catchErrors(storeController.getStoresByTag))

router.get('tags/:tag', catchErrors(storeController.getStoresByTag))
```

2. add controller to `storeController`
	- `getTagsList()` will be a static method that we declare on the `Store`
```js
exports.getStoresByTag = async (req, res) => {
	const stores = await Store.getTagsList()
}
```