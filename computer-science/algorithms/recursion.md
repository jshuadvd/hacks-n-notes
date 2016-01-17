# Recursion

Recursive algorithms call themselves indefinite times until they finish.

## Factorial function

A *factorial* is the product of the integers 1 through $$n$$.

For example: $$5! = 1 * 2 * 3 * 4 * 5 = 120$$

It is useful to calculate the amount of different combinations of a set. Specially useful when doing *permutations and combinations*.

### Implementation 

```javascript
var factorial = function(n) {
    var result = 1;
    
    for(var i = 1; i <= n; i++) {
        result *= i;
    }

    return result;
};
```