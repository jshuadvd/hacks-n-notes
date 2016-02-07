# Merge Sort

> One of the fastest sorting algorithms. Used by general computing and machine learning.

- This is the most important algorithm.
- Discovered by John von Neumann (1945).
- Uses the methodology **divide and conquer**.

### Performance

Θ$$(nlgn)$$

## Pseudo-code

Recursive algorithm composed of two stages:

1. Split the array into halves. Θ(1) 
2. Merge the units in a sorted way. Θ$$(n)$$

The recursive part brings the $$lgn$$ since the splitting creates a *binary tree* data structure which reduces by a power of two each increase of $$n$$.


## Example code

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



