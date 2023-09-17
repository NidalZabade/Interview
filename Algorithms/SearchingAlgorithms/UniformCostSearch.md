# Uniform Cost Search

## What is Uniform Cost Search?

Uniform Cost Search is a graph search algorithm which finds the lowest cost path from a given initial node to any goal node (out of one or more possible goals). It does so by expanding the least cost node.

## Uniform Cost Search Algorithm

The Uniform Cost Search algorithm is as follows:

1. Start at the initial node
2. Explore the neighbor nodes
3. For each explored node, add the unexplored neighbor nodes to a priority queue
4. If the priority queue is empty, stop. Otherwise, take the next node from the priority queue and repeat steps 2 and 3.
5. Repeat steps 2 through 4 until the priority queue is empty.
6. If the goal node is found, stop. Otherwise, take the next node from the priority queue and repeat steps 2 and 3.

## Uniform Cost Search Implementation

A Uniform Cost Search algorithm can be implemented in C as following:

```c
void uniformCostSearch(struct Graph* graph, int startVertex, int goalVertex) {
    struct node* priorityQueue = createNode(startVertex);
    graph->visited[startVertex] = 1;
    struct node* temp = priorityQueue;

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

## Uniform Cost Search Complexity

The time complexity of Uniform Cost Search is O(b<sup>d</sup>), where b stands for branching factor and d stands for depth.

[**Go Back To Searching Algorithms**](README.md)
