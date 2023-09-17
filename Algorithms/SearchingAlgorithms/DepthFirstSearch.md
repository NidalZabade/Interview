# Depth First Search

## What is Depth First Search?

Depth First Search is an algorithm for traversing or searching tree or graph data structures. One starts at the root (selecting some arbitrary node as the root in the case of a graph) and explores as far as possible along each branch before backtracking.

## Depth First Search Algorithm

The Depth First Search algorithm is as follows:

1. Start at the root (or another arbitrarily selected node)
2. Explore the neighbor nodes
3. For each explored node, add the unexplored neighbor nodes to a LIFO stack
4. If the stack is empty, stop. Otherwise, take the next node from the stack and repeat steps 2 and 3.
5. Repeat steps 2 through 4 until the stack is empty.

## Depth First Search Implementation

A Depth First Search algorithm can be implemented in C as following:

```c
void dfs(struct Graph* graph, int startVertex) {
    struct node* stack = createNode(startVertex);
    graph->visited[startVertex] = 1;
    struct node* temp = stack;

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

## Depth First Search Complexity

The time complexity of Depth First Search is O(V+E) when Adjacency Matrix is used, where V stands for vertices and E stands for edges.

[**Go Back To Searching Algorithms**](README.md)
