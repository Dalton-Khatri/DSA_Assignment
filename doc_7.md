# Program 7: Dijkstra's Shortest Path Algorithm

## Overview
Implements Dijkstra's algorithm to find the shortest path from a source vertex to all other vertices in a weighted, undirected graph.

## Data Structures

### Weighted Graph
```c
typedef struct {
    int numVertices;
    int adjMatrix[MAX_VERTICES][MAX_VERTICES];
} WeightedGraph;
```
- adjMatrix[i][j]: Weight of edge between i and j (INF if no edge)

### Algorithm State
- dist[]: Shortest distance from source to each vertex
- visited[]: Whether vertex has been processed
- parent[]: Previous vertex in shortest path (for path reconstruction)

## Functions

1. **createWeightedGraph(int vertices)** - Initializes graph with INF (no edges)
2. **addWeightedEdge(Graph, src, dest, weight)** - Adds weighted edge (undirected)
3. **findMinDistance(dist[], visited[], n)** - Finds unvisited vertex with minimum distance
4. **dijkstra(Graph, src)** - Computes shortest distances and prints paths

## Dijkstra's Algorithm Logic
1. Initialize all distances to INF and visited[] to false; set source distance = 0
2. Repeat until all vertices are visited:
   - Pick unvisited vertex u with smallest distance
   - Mark u as visited
   - Update distances of unvisited neighbors v:
     ```c
     if (dist[u] + weight(u,v) < dist[v]) {
         dist[v] = dist[u] + weight(u,v);
         parent[v] = u;
     }
     ```
3. After processing all vertices, dist[] contains shortest distances, and parent[] allows path reconstruction.

## Main Method

1. Creates weighted graph with numVertices up to 10
2. Adds weighted edges using addWeightedEdge
3. Runs dijkstra(graph, src) from chosen source vertex
4. Prints shortest distances and paths

## Sample Output (simplified)

![Output_7](output/output_7.png "Program 7 output")
