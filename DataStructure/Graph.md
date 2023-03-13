# Graph

## Table of Contents

- [Graph](#graph)
  - [Table of Contents](#table-of-contents)
  - [What is a Graph?](#what-is-a-graph)
  - [Graph Implementation](#graph-implementation)
    - [Adjacency List](#adjacency-list)
    - [Adjacency Matrix](#adjacency-matrix)
  - [Graph Types](#graph-types)
    - [Undirected Graph](#undirected-graph)
    - [Directed Graph](#directed-graph)
## What is a Graph?

A graph is a data structure that stores a collection of nodes and edges. A node is a vertex of a graph. An edge is a connection between two nodes. A graph can be directed or undirected. In a directed graph, an edge is directed from one node to another. In an undirected graph, an edge is undirected and connects two nodes bidirectionally.,

## Graph Implementation

A graph can be implemented using an adjacency list or an adjacency matrix.

### Adjacency List

An adjacency list is a list of lists. Each list represents a node and contains the nodes that are connected to it.

```c
int graph[10][10];
```

### Adjacency Matrix

An adjacency matrix is a two-dimensional array. Each row represents a node and each column represents a node. If the value of an element is 1, it means that the node represented by the row is connected to the node represented by the column.

```c
int graph[10][10];
```

## Graph Types

There are two types of graphs:

* Undirected Graph
* Directed Graph

### Undirected Graph

An undirected graph is a graph in which the edges are undirected and connect two nodes bidirectionally.

### Directed Graph

A directed graph is a graph in which the edges are directed from one node to another.

[**Go Back**](Overview.md)
