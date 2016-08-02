# Spread operator


Spreads an array into its individual values.

```javascript
var a = [1, 2];
var b = returnTwo(a[0], a[1]); // [2, 1]
var c = returnTwo(...a); // [2, 1]
```

## concat arrays with spread

```javascript
let nums = [1, 2, 3];
let abcs = ['a', 'b', 'c'];

let alphanum = [ ...nums, ...abs ]; // [1, 2, 3, 'a', 'b', 'c']
```

## Object.assign shorthand

- This is a [proposal by Sebastian Markbage](https://github.com/sebmarkbage/ecmascript-rest-spread)
- serves as a shorthand for `Object.assign`

```js
const o = {num: 0, txt: 'hi'};
const newO = {...o, num: 1};
```
 
