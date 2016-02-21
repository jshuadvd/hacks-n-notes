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


