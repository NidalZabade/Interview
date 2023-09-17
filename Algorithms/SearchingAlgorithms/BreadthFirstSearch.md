# Breadth First Search

## What is Breadth First Search?

Breadth First Search is an algorithm for traversing or searching tree or graph data structures. It starts at the tree root (or some arbitrary node of a graph, sometimes referred to as a 'search key'[1]), and explores all of the neighbor nodes at the present depth prior to moving on to the nodes at the next depth level.

## Breadth First Search Algorithm

The Breadth First Search algorithm is as follows:

1. Start at the root (or another arbitrarily selected node)
2. Explore the neighbor nodes
3. For each explored node, add the unexplored neighbor nodes to a FIFO queue
4. If the queue is empty, stop. Otherwise, take the next node from the queue and repeat steps 2 and 3.
5. Repeat steps 2 through 4 until the queue is empty.

## Breadth First Search Implementation

A Breadth First Search algorithm can be implemented in C as following:

```c
void bfs(struct Graph* graph, int startVertex) {
    struct node* queue = createNode(startVertex);
    graph->visited[startVertex] = 1;
    struct node* temp = queue;

    while (temp != NULL) {
        int currentVertex = temp->vertex;
        printf("Visited %d \n", currentVertex);
        struct node* temp2 = graph->adjLists[currentVertex];

        while (temp2 != NULL) {
            int adjVertex = temp2->vertex;

            if (graph->visited[adjVertex] == 0) {
                graph->visited[adjVertex] = 1;
                struct node* newNode = createNode(adjVertex);
                temp->next = newNode;
                temp = temp->next;
            }
            temp2 = temp2->next;
        }
        temp = temp->next;
    }
}
```

## Breadth First Search Complexity

The time complexity of Breadth First Search is O(V+E) when Adjacency Matrix is used, where V stands for vertices and E stands for edges.

[**Go Back To Searching Algorithms**](README.md)
