# Prim Algorithm

## What is Prim's Algorithm?

Prim's algorithm is a minimum spanning tree algorithm that finds an edge of the least possible weight that connects any two trees in the forest. It is a greedy algorithm in graph theory as it finds a minimum spanning tree for a connected weighted graph adding increasing cost arcs at each step.

## How does Prim's Algorithm work?

1. Create a set mstSet that keeps track of vertices already included in MST.
2. Assign a key value to all vertices in the input graph. Initialize all key values as INFINITE. Assign key value as 0 for the first vertex so that it is picked first.
3. While mstSet doesn't include all vertices
    1. Pick a vertex u which is not there in mstSet and has minimum key value.
    2. Include u to mstSet.
    3. Update key value of all adjacent vertices of u. To update the key values, iterate through all adjacent vertices. For every adjacent vertex v, if weight of edge u-v is less than the previous key value of v, update the key value as weight of u-v
    4. Repeat step 3 until mstSet doesn't include all vertices

## Prim's Algorithm Example

You can find an example and the implementation on [GeeksforGeeks](https://www.geeksforgeeks.org/prims-minimum-spanning-tree-mst-greedy-algo-5/).

[**Go Back To Greedy Algorithms**](README.md)
