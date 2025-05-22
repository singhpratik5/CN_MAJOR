# Minor 2 Solutions - Computer Networks

## 1. Packet Fragmentation, MTU, and Algorithm
- **Fragmentation:** Large IP packets are split to fit the MTU (Maximum Transmission Unit) of each link.
- **Reassembly:** Done at the destination using fragment offset and identification fields in the IP header.
- **Algorithm to discover MTU:**
  1. Send packets with "Don't Fragment" flag set.
  2. If ICMP "Fragmentation Needed" error is received, reduce packet size and try again.
  3. Repeat until no error is received; this is the path MTU.

---

## 2. Hop Limit in IP Header
- **Field:** TTL (Time To Live) in IPv4, Hop Limit in IPv6.
- **Purpose:** Limits the number of hops a packet can take to prevent infinite loops.
- **Maximum:** 255 (8 bits).
- **Why not time?** Time is hard to measure in routers; hop count is simple and effective.

---

## 3. PING Algorithm using ICMP
- **Steps:**
  1. Sender sends ICMP Echo Request to target.
  2. Target replies with ICMP Echo Reply.
  3. Sender measures round-trip time.
- **Used for:** Checking reachability and measuring delay.

---

## 4. TRACEROUTE Algorithm using ICMP
- **Steps:**
  1. Sender sends packets with increasing TTL (1, 2, 3, ...).
  2. Each router decrements TTL; when TTL = 0, router sends ICMP Time Exceeded message back.
  3. Sender records address of each router along the path.

---

## 5. Host vs. Network Differentiation in CIDR, Advantages/Disadvantages
- **Host part:** Identifies individual device.
- **Network part:** Identifies network segment.
- **CIDR Advantages:** Efficient address allocation, reduces routing table size.
- **Disadvantages:** More complex, requires longest prefix match.
- **Comparison:**
  - Classful: Fixed boundaries (A, B, C)
  - CIDR: Flexible boundaries (e.g., /20, /27)

---

## 6. Dijkstra's Algorithm (Shortest Path)
- **Steps:**
  1. Set distance to source = 0, all others = infinity.
  2. Mark source as visited.
  3. For each neighbor, update distance if shorter path found.
  4. Select unvisited node with smallest distance, repeat.
  5. Continue until all nodes visited.
- **Apply to graph:** Draw the graph, show distance updates at each step.

---

## 7. Distance Vector Routing Algorithm
- **How it works:** Each node shares its distance vector (cost to all nodes) with neighbors.
- **Update rule:**
  D(x, y) = min { c(x, v) + D(v, y) } for all neighbors v
- **Apply to graph:** For each node, update table based on neighbors' info until no changes. 