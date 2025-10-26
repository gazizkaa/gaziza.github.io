# City Transportation Network Optimization (MST Project)

## Overview

This project implements **Prim’s** and **Kruskal’s algorithms** to optimize a city’s transportation network.  
The goal is to determine the **minimum set of roads** connecting all districts with the **lowest total construction cost**.

Graphs are read from JSON files, and each algorithm calculates:

- List of edges forming the MST  
- Total cost of the MST  
- Number of operations performed (algorithm-specific)  
- Execution time in milliseconds  

The results are compared to analyze efficiency and performance.

---

## Input Data

Input is a JSON file containing a list of graphs. Each graph includes:

- `id`: Graph identifier  
- `nodes`: List of district names  
- `edges`: List of edges with `from`, `to`, and `weight`  

---

## Running the Project

### Build with Maven

```bash
mvn clean compile
Run the Program
bash
Copy code
mvn exec:java -Dexec.mainClass="com.example.mst.Main"
Output: Results for each graph are printed to the console and stored in output.json.

MST Algorithms
Prim’s Algorithm
Greedily grows the MST by always adding the minimum weight edge connecting a vertex in the MST to a vertex outside.
Complexity: O(E log V) using a priority queue.

Kruskal’s Algorithm
Greedily adds edges in order of increasing weight, skipping edges that would form cycles.
Complexity: O(E log E) using Union-Find.

Results


From the conducted experiments on graphs of different sizes and densities, both Prim’s and Kruskal’s algorithms successfully computed the Minimum Spanning Tree (MST) with identical total costs for all graphs, confirming correctness.

Small Graphs (4–5 vertices)
Graph 1 (5 vertices, 7 edges):
Prim: 12 operations, 3.07 ms
Kruskal: 11 operations, 0.73 ms

Graph 2 (4 vertices, 5 edges):
Prim: 8 operations, 0.02 ms
Kruskal: 8 operations, 0.01 ms

Observation: On small graphs, both algorithms are extremely fast. Kruskal often executes slightly faster due to fewer internal steps, though differences are negligible.

Medium Graphs (10–12 vertices)
Graph 1 (10 vertices, 14 edges):
Prim: 23 operations, 1.90 ms
Kruskal: 23 operations, 1.08 ms

Graph 2 (12 vertices, 15 edges):
Prim: 26 operations, 0.14 ms
Kruskal: 26 operations, 0.06 ms

Observation: For medium-sized graphs, Kruskal tends to execute slightly faster, though both scale well. The number of operations grows with graph size but remains practical.

Large Graphs (20 vertices, 23 edges)
Graph 1:
Prim: 44 operations, 5.86 ms
Kruskal: 42 operations, 1.34 ms

Observation: On larger, sparser graphs, Kruskal shows better execution times due to efficient union-find management. Prim takes longer as the number of vertices grows.

Efficiency Comparison
Prim’s Algorithm
Efficient for dense graphs where edges are close to V²

Slightly slower on large sparse graphs due to priority queue overhead

Easier to implement with adjacency matrices or lists for dense graphs

Kruskal’s Algorithm
Performs better on sparse graphs using sorted edges and union-find

Scales well for larger graphs with fewer edges

Simpler edge-based logic but requires sorting upfront

Practical Insight:

Small graphs: either algorithm is fine

Medium graphs: Kruskal slightly faster

Large sparse graphs: Kruskal preferable

Dense graphs: Prim may be preferred if adjacency structures are used

Conclusion
Both algorithms consistently produce MSTs with identical total costs.

Sparse graphs: Kruskal is generally faster

Dense graphs: Prim can be advantageous

Small graphs: Either is sufficient

The number of operations grows with graph size, but execution time differences are only significant for larger datasets.

yaml
Copy code

---

If you want, I can also **add a placeholder for the MST graph image** with instructions so anyone can just drag-and-drop an image into the repo and it will display correctly.  

Do you want me to do that?











