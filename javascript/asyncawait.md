# AsyncAwait

Any function with the `async` flag will return a promise.

Any function call with `await` will wait until the promise is resolved.

### To avoid using try catch

```js
async function iCallAPromise() {
  const result = await fetchUsers().catch(error => error);
  console.log(result);
}
```
