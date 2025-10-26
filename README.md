# City Transportation Network Optimization (MST Project)

## Overview

This project implements **Prim’s** and **Kruskal’s algorithms** to optimize a city’s transportation network.  
The goal is to determine the **minimum set of roads** connecting all districts with the **lowest total construction cost**.

Graphs are read from JSON files and each algorithm calculates:
- List of edges forming the MST  
- Total cost of the MST  
- Number of operations performed (algorithm-specific)  
- Execution time in milliseconds  

The results are compared to analyze efficiency and performance.

---

## Project Structure

mst/
├── src/
│ └── main/
│ └── java/com/example/mst/
│ ├── Main.java # Runs MST algorithms
│ ├── GraphData.java # Represents graph structure
│ ├── EdgeData.java # Represents edges
│ ├── JsonReader.java # Reads graph JSON input
│ ├── Prim.java # Prim’s algorithm
│ └── Kruskal.java # Kruskal’s algorithm
├── input.json # Example input graphs
├── output.json # MST results in JSON format
├── pom.xml # Maven configuration
└── README.md # Project report
---

## Input Data

Input is a JSON file with a list of graphs. Each graph contains:
- `id`: Graph identifier  
- `nodes`: List of district names  
- `edges`: List of edges with `from`, `to`, and `weight` Running the Project

Build with Maven:

mvn clean compile


Run the program:

mvn exec:java -Dexec.mainClass="com.example.mst.Main"


Output: Results for each graph are printed to the console and stored in output.json.

MST Algorithms
Prim’s Algorithm

Greedily grows the MST by always adding the minimum weight edge connecting a vertex in the MST to a vertex outside.

Complexity: O(E log V) using a priority queue.

Kruskal’s Algorithm

Greedily adds edges in order of increasing weight, skipping edges that would form cycles.

Complexity: O(E log E) using Union-Find.

## Results
## Conclusion

Both algorithms produce the same MST total cost, confirming correctness.

Prim tends to be slightly slower on large graphs due to priority queue operations.

Kruskal is more efficient on sparse graphs because sorting edges is cheaper than updating a priority queue.

Recommendation: Use Kruskal for sparse networks and Prim for dense graphs.
