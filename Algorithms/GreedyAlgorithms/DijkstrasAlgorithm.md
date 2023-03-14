# Dijkstra's Algorithm

## What is Dijkstra's Algorithm?

Dijkstra's algorithm is a shortest path algorithm that finds the shortest path between two nodes in a [**graph**](../../DataStructure/Graph.md). It is a greedy algorithm in graph theory as it finds a shortest path between two nodes for a connected weighted graph adding increasing cost arcs at each step.

## How does Dijkstra's Algorithm work?

1. Create a set sptSet (shortest path tree set) that keeps track of vertices already included in shortest path tree, i.e., whose minimum distance from source is calculated and finalized. Initially, this set is empty.
2. Assign a distance value to all vertices in the input graph. Initialize all distance values as INFINITE. Assign distance value as 0 for the source vertex so that it is picked first.
3. While sptSet doesn't include all vertices
    1. Pick a vertex u which is not there in sptSet and has minimum distance value.
    2. Include u to sptSet.
    3. Update distance value of all adjacent vertices of u. To update the distance values, iterate through all adjacent vertices. For every adjacent vertex v, if sum of distance value of u (from source) and weight of edge u-v, is less than the distance value of v, then update the distance value of v.
    4. Repeat step 3 until sptSet doesn't include all vertices

## Dijkstra's Algorithm Example

You can find an example and the implementation on [GeeksforGeeks](https://www.geeksforgeeks.org/dijkstras-shortest-path-algorithm-greedy-algo-7/).

[**Go Back To Greedy Algorithms**](README.md)
