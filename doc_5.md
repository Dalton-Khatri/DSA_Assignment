# Program 5: Graph Traversal - BFS and DFS

## Overview
Implements an undirected graph using adjacency matrix representation and performs Breadth-First Search (BFS) and Depth-First Search (DFS) traversals.

## Graph Representation

The graph is stored as an adjacency matrix where:

- `graph[i][j] = 1` indicates an edge between vertex `i` and vertex `j`
- `graph[i][j] = 0` indicates no edge

---

## Functions

### 1. Breadth First Search (BFS)

```c
void BFS(int graph[MAX][MAX], int vertices, int start);
```

- Traverse the graph level by level
- Uses a queue (FIFO)
- Ensures all adjacent vertices are visited before moving deeper

### 2. Depth First Search (DFS)

```c
void DFS(int graph[MAX][MAX], int vertices, int v, int visited[]);

```

- Traverses the graph depth-wise
- Uses recursion (implicit stack)
- Visits a vertex and explores as far as possible before backtracking


## Main Method

1. Defines the number of vertices
2. Initializes the adjacency matrix of the graph
3. Displays the adjacency matrix
4. Calls BFS starting from vertex 0
5. Calls DFS starting from vertex 0

## Sample Output

![Output_5](output/output_5.png "Program 5 output")