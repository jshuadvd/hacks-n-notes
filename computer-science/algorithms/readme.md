# Algorithms

## Types of algorithms

type | example use case
---- | ----------------
Compression algorithm | (video/audo streaming)
Route finding algorithm | Google maps directions
Rendering algorithm | Determine how to display the lightning in a 3D rendered object
Optimization & Scheduling algorithm | To arrange the solar panels in satellites
Minimax algorithms | Checkers
 
 
## Important authors

- Thomas Cormen
- Devin Balkom

### Search Algorithms

#### Binary Search Algorithm

Finds items from an ordered list.

##### Steps

- Divide half portion of the list that could contain the searched item.
- Repeat until narrow to one item.

## Sort algorithm performance comparison

Name | Best | Average | Worst | Memory | Stable
---- | ---- | ------- | ----- | ------ | ------
Bubble Sort | $$n$$ | $$n^2$$ | $$n^2$$ | 1 | Yes
Selection Sort | $$n^2$$ | $$n^2$$ | $$n^2$$ | 1 | No
Insertion Sort | $$n$$ | $$n^2$$ | $$n^2$$ | 1 | Yes
Merge Sort | $$nlogn$$ | $$nlogn$$ | $$nlogn$$ | worst case is n | Yes
Quick Sort | $$nlogn$$ | $$nlogn$$ | $$n^2$$ | $$logn$$ on avg. Worst $$n$$| No
Heap Sort | $$nlogn$$ | $$nlogn$$ | $$nlogn$$ | 1 | No
