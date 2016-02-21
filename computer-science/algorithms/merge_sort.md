# Merge Sort

> One of the fastest sorting algorithms. Used by general computing and machine learning.

- This is the most important sorting algorithm.
- Discovered by John von Neumann (1945).
- Uses the methodology **divide and conquer**.
    
### Performance

Θ$$(nlgn)$$

## Pseudo-code

Recursive algorithm composed of two stages:

1. Split the array into halves. Θ(1) 
2. Merge the units in a sorted way. Θ$$(n)$$

The recursive part brings the $$lgn$$ since the splitting creates a *binary tree* data structure which reduces by a power of two each increase of $$n$$.

## My example code using recursion 

[](codepen://cuadraman/pgGqpa?height=440)

```javascript

/**
 * sorts and merge two sub arrays.
 * Written in a recursive functional programming.
 * Free of side-effects.
 *
 * Concatenating arrays before returning,
 * to use Proper Tail Call optimization.
 *
 * @param {array} sorted
 * @param {array} subA
 * @param {array} subB
 * @result {array} final sorted array
 */
function merge (sorted, subA, subB ) {
  if (!subA.length && !subB.length) {
    return sorted;
  }

  if (!subA.length && subB.length) {
    const newSorted = [...sorted, ...subB];
    return newSorted;
  }

  if (subA.length && !subB.length) {
    const newSorted2 = [...sorted, ...subA];
    return newSorted2;
  }

  if (subA[0] <= subB[0]) {
    const newSubA = subA.slice(1);
    const newSorted3 = [ ...sorted, subA[0] ];
    return merge(newSorted3, newSubA, subB);
  }

  const newSubB = subB.slice(1);
  const newSorted4 = [ ...sorted, subB[0] ];
  return merge(newSorted4, subA, newSubB);
}

function mergeSort (array) {
  if (array.length <= 1) {
    return array;
  }

  if (array.length === 2) {
    const subA2 = [array[0]];
    const subB2 = [array[1]];
    const sorted = merge([], subA2, subB2);
    return sorted;
  }

  const midIndex = Math.floor( (array.length) / 2 );
  const subA = mergeSort( array.slice(0, midIndex) );
  const subB = mergeSort( array.slice(midIndex) );
  const sorted2 = merge([], subA, subB);
  return sorted2;
}

// Unit tests

// Test1
const sorted = merge([], [3,5], [2,6]);
const should = [2,3,5,6];
console.log(`
  Test merge():
  ${sorted.toString() === should.toString()}:
  ${sorted.toString()} should be ${should}
`);

// Test2
const sorted2 = merge([], [5,3], [2,6]);
const should2 = [2,3,5,6];
console.log(`
  Test2 merge():
  This should not sort correctly since the sub arrays arenot sorted.
  ${sorted2.toString() !== should2.toString()}:
  ${sorted2.toString()} should not be ${should2}
`);

// Test3
const array = [5,3,2,6];
const should3 = [2, 3, 5, 6];
const sorted3 = mergeSort(array);
console.log(`
  Test3 mergeSort(${array.toString()}):
  ${sorted3.toString() === should3.toString()}:
  ${sorted3.toString()} should be ${should3}
`);

// Test4
const array2 = [-2,5,0,7];
const should4 = [-2, 0, 5, 7];
const sorted4 = mergeSort(array2);
console.log(`
  Test4 mergeSort(${array2.toString()}):
  Should handle negative numbers and 0's.
  ${sorted4.toString() === should4.toString()}:
  ${sorted4.toString()} should be ${should4}
`);

// Test5
const array3 = [1, 3, 4, 7];
const should5 = [1, 3, 4, 7];
const sorted5 = mergeSort(array3);
console.log(`
  Test5 mergeSort(${array3.toString()}):
  Should work with sorted arrays.
  ${sorted5.toString() === should5.toString()}:
  ${sorted5.toString()} should be ${should5}
`);

// Test6
const array4 = [ 1, 209, 8, 80, 3, 7, 0 ];
const should6 = [ 0, 1, 3, 7, 8, 80, 209 ];
const sorted6 = mergeSort(array4);
console.log(`
  Test6 mergeSort(${array4.toString()}):
  Should work with long and odd length arrays
  ${sorted6.toString() === should6.toString()}:
  ${sorted6.toString()} should be ${should6}
`);

// Display initial array in HTML
const initElement = document.querySelector('.init');
initElement.textContent = array.toString();

// Display sorted array in HTML
const resultElement = document.querySelector('.result');
const resultContent = mergeSort(array);
resultElement.textContent = resultContent.toString();
```

## Example code from Khan Academy

```javascript

// Takes in an array that has two sorted subarrays,
//  from [p..q] and [q+1..r], and merges the array
var merge = function(array, p, q, r) {
    var lowHalf = [];
    var highHalf = [];

    var k = p;
    var i;
    var j;
    for (i = 0; k <= q; i++, k++) {
        lowHalf[i] = array[k];
    }
    for (j = 0; k <= r; j++, k++) {
        highHalf[j] = array[k];
    }

    k = p;
    i = 0;
    j = 0;
    
    // Repeatedly compare the lowest untaken element in
    //  lowHalf with the lowest untaken element in highHalf
    //  and copy the lower of the two back into array
    while (i < lowHalf.length && j < highHalf.length) {
        if (lowHalf[i] < highHalf[j]) {
            array[k] = lowHalf[i];
            i++;
        } else {
            array[k] = highHalf[j];
            j++;
        }
        k++;
    }
    
    // Once one of lowHalf and highHalf has been fully copied
    //  back into array, copy the remaining elements from the
    //  other temporary array back into the array
    while (i < lowHalf.length) {
        array[k] = lowHalf[i];
        k++;
        i++;
    }
    while (j < highHalf.length) {
        array[k] = highHalf[j];
        k++;
        j++;
    }
};

// Takes in an array and recursively merge sorts it
var mergeSort = function(array, p, r) {
    if (r > p) {
        var q = Math.floor((r - p) / 2 + p);
        mergeSort(array, p, q);
        mergeSort(array, q + 1, r);
        merge(array, p, q, r);
    }
};

var array = [14, 7, 3, 12, 9, 11, 6, 2];
mergeSort(array, 0, array.length-1);
```



