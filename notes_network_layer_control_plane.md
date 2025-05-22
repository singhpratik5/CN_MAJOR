# Network Layer: Control Plane - Exam Notes (Detailed)

## 1. Overview
- The Control Plane is responsible for routing decisions and distributing routing information between routers.
- Main algorithms: Distance Vector, Link State.

## 2. Key Algorithms and Protocols

### 2.1 Distance Vector Algorithm
- **How it works:** Each router shares its routing table with neighbors periodically.
- **Bellman-Ford Equation:**
  - D(x, y) = min { c(x, v) + D(v, y) } for all neighbors v
    - D(x, y): cost from x to y
    - c(x, v): cost from x to neighbor v
- **Count-to-infinity problem:** Slow convergence when a link fails.
- **Example Protocol:** RIP (Routing Information Protocol)
  - RIP uses hop count as metric, max 15 hops.

### 2.2 Link State Algorithm
- **How it works:** Each router floods the network with information about its links (link state advertisements).
- Each router builds a complete map of the network and computes shortest paths using Dijkstra's algorithm.
- **Example Protocol:** OSPF (Open Shortest Path First)
  - OSPF uses cost as metric, supports large and hierarchical networks.

### 2.3 Dijkstra's Algorithm (Shortest Path First)
- **Steps:**
  1. Start with source node, set distance to 0, all others to infinity.
  2. Mark source as visited.
  3. For each neighbor, update distance if shorter path found.
  4. Select unvisited node with smallest distance, repeat.
  5. Continue until all nodes visited.
- **Example:**
  - Draw a graph, show step-by-step updates of distances and predecessors.

### 2.4 Routing Tables
- **Structure:** Destination | Next Hop | Metric (cost/hop count)
- **Updated by:** Routing protocols (RIP, OSPF)

## 3. Example Questions
1. Explain the working of the Distance Vector Algorithm with an example.
2. Compare Distance Vector and Link State Routing. List pros and cons.
3. Describe the steps of Dijkstra's algorithm for shortest path with a sample graph.
4. What are the advantages of OSPF over RIP?
5. Draw a sample routing table and explain how it is updated.

## 4. Exam Tips
- Practice Dijkstra's algorithm with sample graphs.
- Draw diagrams for routing tables and network topologies.
- Know the differences between RIP, OSPF, and Link State protocols.
- Be able to explain count-to-infinity and how OSPF avoids it. 