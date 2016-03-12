# Graph representation

> Graphs are connections between entities.

- The social network is a graph.

term | definition
-- | --
vertices | entities in the graph
vertex | a single entity
edge | a line representing the connection between two vertices
undirected graph | a graph which edges go both ways
directed graph | a graph which edges have one direction flow
adjacent or incident | when two vertices are connected
neighbors | a vertex refering to another adjacent vertex
degree | the amount of edges between two vertices
path | the sequential edges that connect two vertices
shortest path | the path with less edges
cycle | a path that reconnects with the origin vertex
acyclic graph | a path with no cycles
dag | an *acyclic graph*
to leave | when a directed edge points out of a vertex
to enter | when a directed edge points into a vertex
out-degree | the number of edges pointing out of a vertex
in-degree | the number of edges pointing into a vertex


## Weighted graph

> The edges can have a numeric weight.

For example, a weight can be the distance between two cities (*vertices*).

## Use cases

- Social networks
- road maps
- flowcharts
- dependency flow charts

## Representation

- *vertices* are mostly names as numbers.

### Criteria
1. How much memory or space we need in each representation
2. How long will it take to determine whether a given *edge* is in the graph
3. How long it takes to find the *neighbors* of a given *vertex*

### Representation types

#### 1. Edge List

