# Quick Sort

> Sorting algorithm

- Uses *divide and conquer* strategy.
- Recursive algorithm.
- The divide step does most of the work.
- The merge step does nothing.

## Performance

Worst case | Best case
---------- | ---------
Θ($$n^2$$) | Θ($$nlogn$$)

> In practice *Quick Sort* outperforms *Merge Sort*, *Insertion Sort* and *Selection Sort*.

## Pseudo-code

### Divide

Divide by choosing any element (pivot) in the sub-array **array[p..r]**.

#### Partition

1. Arrange the elements smaller than **pivot** to its left.
2. Then arrange the elements bigger than the **pivot** to its right.
3. The elements don't have to be in order. Just to the correct side of the **pivot**.

### Conquer

Recursively call the divide step until the sub-arrays less than 2 elements long.

### Combine

Just concatenate the sub-arrays. Since the elements got sorted on the partitioning, there is no work left to do.


## My example


[](codepen://cuadraman/QyYqEZ)

```javascript

function partition (array, leftArray, rightArray, pivot) {
  if (!array.length) {
    return {leftArray, rightArray};
  }
  
  const newLeftArray = array[0] < pivot ?
    [...leftArray, array[0]] :
    leftArray.slice(0);
        
  const newRightArray = array[0] < pivot ?
    rightArray.slice(0) :
    [...rightArray, array[0]];
  
  const newArray = array.slice(1);
        
  return partition(newArray, newLeftArray, newRightArray, pivot);
}

function quickSort (array) {
  // When to stop
  if (array.length < 2) {
    return array;
  }
  // Divide
  const pivot = array[array.length - 1];
  const { leftArray, rightArray } = partition(
    array.slice(0, array.length - 1), [], [], pivot);
  // Conquer
  const sortedLeftArray = quickSort(leftArray);
  const sortedRightArray = quickSort(rightArray)
  const sortedArray = [...sortedLeftArray, pivot, ...sortedRightArray];
  return sortedArray;
}
```
