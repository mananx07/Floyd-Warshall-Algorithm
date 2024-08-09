# Floyd-Warshall Algorithm
## Overview
The Floyd-Warshall algorithm is a dynamic programming algorithm used to find the shortest paths between all pairs of vertices in a weighted graph. This algorithm is particularly useful for graphs with negative weight edges, but it doesn't work if the graph contains negative weight cycles.


## How the Algorithm Works
The algorithm operates by iteratively improving the solution for the shortest path between any two vertices by considering each vertex as an intermediate point in the path. It maintains a matrix dist[][], where dist[i][j] is the shortest distance from vertex i to vertex j.


## Steps:
### 1. Initialization:
The dist[][] matrix is initialized to the input graph matrix, where dist[i][j] is set to the weight of the edge from i to j, or INF if no edge exists between them.

### 2. Main Loop:
The algorithm then iteratively checks if a path from vertex i to vertex j via vertex k is shorter than the current known path:
$$ dist[i][j]=min(dist[i][j],dist[i][k]+dist[k][j]) $$
This process is repeated for each vertex k (0 to V-1).

### 3. Output:
The final dist[][] matrix contains the shortest path distances between every pair of vertices. If dist[i][j] is INF, it means there is no path from vertex i to vertex j.


## Time Complexity
The time complexity of the Floyd-Warshall algorithm is O(V^3) where V is the number of vertices in the graph.

## Functions
* **floydWarshall(int graph[][V])**: Implements the Floyd-Warshall algorithm.
* **printSolution(int dist[][V])**: Prints the shortest distance between every pair of vertices.

## Limitations
* Cannot handle graphs with negative weight cycles.

* Memory complexity is $$ O(V^3) $$