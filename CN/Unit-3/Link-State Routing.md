# **Link-State Routing and Routers — (15 Marks Answer)**

---

## **1. Introduction**

* **Routing** is the process of determining the best path for data packets to travel from the source to the destination across a network.
* In **Link-State Routing**, each router has **complete knowledge of the network topology**.
* Every router **independently calculates the shortest path** to every other router using **Dijkstra’s shortest path algorithm**.
* This method is more reliable and faster to converge than **Distance Vector Routing** (like RIP).

---

## **2. Basic Concept of Link-State Routing**

Each router performs the following main steps:

1. **Discover its neighbors** and learn their network addresses.
2. **Measure the cost (metric)** to each neighbor (can be hop count, delay, bandwidth, etc.).
3. **Create a link-state packet (LSP)** containing this information.
4. **Flood the LSP** to all other routers in the internetwork.
5. **Build a complete network topology map** using the collected LSPs.
6. **Compute the shortest path** to each destination using **Dijkstra’s Algorithm**.

---

## **3. Reliable Flooding**

* Flooding ensures that **every router receives a copy of every other router’s LSP**.
* Each LSP is sent out on **all directly connected links**.
* When a router receives an LSP, it:

  * Checks if it already has a **newer copy**.
  * If the received LSP is **newer (higher sequence number)**, it stores it and forwards it to all other neighbors.
* This continues until all routers in the network receive the latest LSP.

**Purpose:** Ensures all routers have the **same and updated link-state database**.

---

### **Diagram: Flooding of Link-State Packets**

```
(a) LSP arrives at node X
(b) X floods LSP to A and C
(c) A and C flood LSP to B (but not X)
(d) Flooding is complete
```

---

## **4. Link-State Packet (LSP) Format**

Each **LSP (Link-State Packet)** contains the following fields:

1. **ID of the node** that created the LSP.
2. **List of directly connected neighbors** of that node with **cost of each link**.
3. **Sequence Number** – helps identify newer information.
4. **Time to Live (TTL)** – prevents old LSPs from circulating indefinitely.

### **Functions:**

* Fields (1) & (2): used for **route calculation**.
* Fields (3) & (4): used for **reliable flooding and aging**.

---

## **5. Route Calculation using Dijkstra’s Algorithm**

After all routers receive the LSPs and build a topology map, each router runs **Dijkstra’s Shortest Path Algorithm** to determine the optimal path to every destination.

### **Algorithm Steps:**

1. **Initialize** the Confirmed List with an entry for the source node (cost = 0).
2. For the node just added, **examine all its neighbors**.
3. For each neighbor:

   * Compute the **total cost** to reach that neighbor through the current node.
   * If this path is shorter than the previously known path, **update** it.
4. Select the **neighbor with the smallest cost**, move it to the Confirmed List.
5. Repeat until all nodes are added to the Confirmed List.

---

### **Example:**

Suppose node D runs Dijkstra’s algorithm.
It starts with itself in the confirmed list and gradually adds nodes with lowest cumulative cost until all nodes are included.
The result is a **shortest-path tree** rooted at node D.

---

## **6. Properties of Link-State Routing**

| **Property**                      | **Description**                                      |
| --------------------------------- | ---------------------------------------------------- |
| **Fast Convergence**              | Network stabilizes quickly after a change.           |
| **Low Traffic Overhead**          | LSPs are only sent when topology changes.            |
| **Accurate Topology Information** | Each router has the same global view of the network. |
| **Independent Computation**       | Each router independently computes the best paths.   |
| **Rapid Failure Detection**       | Uses “Hello” packets to check neighbor availability. |

---

## **7. Disadvantages**

* Requires **more memory** (to store entire topology).
* **Complex computation** (Dijkstra algorithm at each router).
* **Flooding** can cause temporary overhead during topology changes.

---

## **8. Open Shortest Path First (OSPF)**

* **OSPF** is the most widely used **link-state routing protocol** in modern networks.
* It adds features like:

  1. **Authentication** of routing messages.
  2. **Hierarchical areas** (Backbone area 0, Area border routers).
  3. **Load balancing** (equal-cost paths can share traffic).
* OSPF divides an autonomous system into **areas** to reduce complexity and LSP flooding overhead.

### **OSPF Message Types:**

1. **Hello Message** – checks if neighbors are alive.
2. **Database Description (DD)** – summary of LSPs.
3. **Link-State Request (LSR)** – requests specific LSPs.
4. **Link-State Update (LSU)** – sends LSPs.
5. **Link-State Acknowledgment (LSAck)** – confirms receipt.

---

## **9. Comparison: Distance Vector vs Link State**

| **Feature**       | **Distance Vector (RIP)**           | **Link State (OSPF)**       |
| ----------------- | ----------------------------------- | --------------------------- |
| **Knowledge**     | Knows only neighbors’ distance info | Knows full network topology |
| **Updates**       | Periodic                            | On topology change          |
| **Algorithm**     | Bellman–Ford                        | Dijkstra                    |
| **Convergence**   | Slow                                | Fast                        |
| **Scalability**   | Limited                             | High                        |
| **Routing Loops** | Possible                            | Avoided                     |
| **Overhead**      | Less                                | More memory needed          |

---

## **10. Summary**

* **Link-State Routing** builds a complete map of the network using **LSP flooding**.
* Each router runs **Dijkstra’s algorithm** to compute the **shortest path** to all destinations.
* **OSPF** is the practical implementation of link-state routing in the Internet.
* Provides **fast convergence, reliability, and scalability**, making it ideal for large and complex networks.

---

### **Diagram Summary (for Exam)**

```
Router A ---- 10 ---- Router B
   |                       |
  20                      15
   |                       |
Router C ---- 30 ---- Router D
```

Each router advertises link cost → all routers get same map → run Dijkstra → shortest paths.
