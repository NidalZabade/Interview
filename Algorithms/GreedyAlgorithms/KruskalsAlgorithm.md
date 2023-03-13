# Kruskal's Algorithm

## What is Kruskal's Algorithm?

Kruskal's algorithm is a minimum spanning tree algorithm that finds an edge of the least possible weight that connects any two trees in the forest. It is a greedy algorithm in graph theory as it finds a minimum spanning tree for a connected weighted graph adding increasing cost arcs at each step.

## How does Kruskal's Algorithm work?

1. Create a forest F (a set of trees), where each vertex in the graph is a separate tree.
2. Create a set S containing all the edges in the graph.
3. While S is nonempty and F is not yet spanning:
    1. Remove an edge with minimum weight from S
    2. If the removed edge connects two different trees then add it to the forest F, combining two trees into a single tree.
    3. Otherwise discard the edge.

## Kruskal's Algorithm Example

You can find an example and the implementation on [GeeksforGeeks](https://www.geeksforgeeks.org/kruskals-minimum-spanning-tree-algorithm-greedy-algo-2/).

[**Go Back To Greedy Algorithms**](Overview.md)
