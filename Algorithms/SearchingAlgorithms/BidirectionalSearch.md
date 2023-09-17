# Bidirectional Search

## What is Bidirectional Search?

Bidirectional Search is a graph search algorithm which find smallest path form source to goal vertex. It runs two simultaneous searches: one forward from the initial state, and one backward from the goal, stopping when the two meet in the middle. The reason for using two simultaneous searches is that the complexity of finding the intersection of two searches is much less than that of finding a single search from the root node to the goal.

## Bidirectional Search Algorithm

The Bidirectional Search algorithm is as follows:

1. Start at the source and the goal vertex
2. Explore the neighbor nodes of the source vertex
3. Explore the neighbor nodes of the goal vertex
4. For each explored node, add the unexplored neighbor nodes to a FIFO queue
5. If the queue is empty, stop. Otherwise, take the next node from the queue and repeat steps 2 and 3.
6. Repeat steps 2 through 5 until the queue is empty.
7. If the source and goal vertex are the same, stop. Otherwise, take the next node from the queue and repeat steps 2 and 3.

## Bidirectional Search Implementation

A Bidirectional Search algorithm can be implemented in C as following:

```c
void bidirectionalSearch(struct Graph* graph, int startVertex, int goalVertex) {
    struct node* queue1 = createNode(startVertex);
    struct node* queue2 = createNode(goalVertex);
    graph->visited[startVertex] = 1;
    graph->visited[goalVertex] = 1;
    struct node* temp1 = queue1;
    struct node* temp2 = queue2;

    while (temp1 != NULL && temp2 != NULL) {
        int currentVertex1 = temp1->vertex;
        int currentVertex2 = temp2->vertex;
        printf("Visited %d \n", currentVertex1);
        printf("Visited %d \n", currentVertex2);
        struct node* temp3 = graph->adjLists[currentVertex1];
        struct node* temp4 = graph->adjLists[currentVertex2];

        while (temp3 != NULL) {
            int adjVertex = temp3->vertex;

            if (graph->visited[adjVertex] == 0) {
                graph->visited[adjVertex] = 1;
                struct node* newNode = createNode(adjVertex);
                temp1->next = newNode;
                temp1 = temp1->next;
            }
            temp3 = temp3->next;
        }

        while (temp4 != NULL) {
            int adjVertex = temp4->vertex;

            if (graph->visited[adjVertex] == 0) {
                graph->visited[adjVertex] = 1;
                struct node* newNode = createNode(adjVertex);
                temp2->next = newNode;
                temp2 = temp2->next;
            }
            temp4 = temp4->next;
        }
        temp1 = temp1->next;
        temp2 = temp2->next;
    }
}
```

## Bidirectional Search Complexity

The time complexity of Bidirectional Search is O(b^d/2) where b is the branching factor and d is the depth of the shallowest goal.

[**Go Back To Searching Algorithms**](README.md)
