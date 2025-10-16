# 🛰️ **Routing Information Protocol (RIP) and Distance Vector Routing**

*(15 Marks Answer)*

---

## **1. Introduction to Routing**

* **Routing** is the process of selecting the best path in a network along which data packets can travel from the **source** to the **destination**.
* Each router maintains a **routing table** that stores the **next hop** to reach a destination network.
* Routing algorithms are classified as:

  * **Distance Vector Routing (e.g., RIP)**
  * **Link-State Routing (e.g., OSPF)**

---

## **2. What is Routing Information Protocol (RIP)?**

* **RIP (Routing Information Protocol)** is an **Interior Gateway Protocol (IGP)** used for routing **within an Autonomous System (AS)**.
* RIP is based on the **Distance Vector Routing Algorithm** (Bellman–Ford Algorithm).
* It was originally defined in **RFC 1058** and later updated as **RIP version 2 (RFC 2453)**.

---

### **Key Features of RIP:**

| Feature                     | Description                                  |
| --------------------------- | -------------------------------------------- |
| **Routing Type**            | Distance Vector                              |
| **Metric Used**             | Hop count (number of routers to destination) |
| **Maximum Hop Count**       | 15 (16 = Infinity → unreachable)             |
| **Update Interval**         | Every 30 seconds                             |
| **Transport Protocol**      | UDP (Port 520)                               |
| **Administrative Distance** | 120                                          |
| **Scope**                   | Used inside small and medium-sized networks  |

---

## **3. Distance Vector Routing – Concept**

* Each router **knows the distance (metric)** to every other network and the **next hop** to reach it.
* Each router **periodically shares** its entire routing table with its **immediate neighbors** only.
* After receiving updates, the router **recalculates** its routing table using the **Bellman-Ford algorithm**.

---

### **How It Works:**

1. Each router initially knows only the **distance to its directly connected networks (cost = 1)**.
2. Routers periodically **exchange routing tables** with their **neighbors**.
3. Each router updates its own table:

   * Adds **1 hop** to each received distance.
   * Compares new paths with existing ones.
   * Keeps the **shortest path** (fewest hops).
4. The process continues until all routers have consistent routing tables — known as **convergence**.

---

### **Example:**

Suppose there are three routers: **A**, **B**, and **C**.

```
A ---- B ---- C
```

* A knows route to itself (cost = 0).
* B tells A that it can reach C in 1 hop.
* A updates:

  * A → C = 2 hops (A→B→C).
* Similarly, all routers learn shortest paths via neighbor updates.

---

## **4. Bellman-Ford Algorithm (Used in RIP)**

The **Bellman–Ford algorithm** is used to calculate the shortest path in Distance Vector Routing.

### **Algorithm Steps:**

1. **Initialize** the routing table:

   * Distance to itself = 0
   * Distance to all others = ∞
2. **Receive** routing information from neighbors.
3. **Update Rule:**

   ```
   D(X, Y) = min [ D(X, N) + D(N, Y) ]
   ```

   where:

   * D(X, Y) = distance from router X to destination Y
   * N = neighbor of router X
   * D(N, Y) = distance from neighbor N to destination Y
4. **Repeat** periodically until no change occurs (network convergence).

---

## **5. Routing Table Example**

| **Destination** | **Next Hop** | **Distance (Hop Count)** |
| --------------- | ------------ | ------------------------ |
| Network 1       | Direct       | 0                        |
| Network 2       | Router B     | 1                        |
| Network 3       | Router C     | 2                        |

Routers periodically share and update this table to maintain accurate routes.

---

## **6. Updates in Distance Vector Routing**

There are **two types of updates** in RIP:

1. **Periodic Update:**

   * Sent every 30 seconds to all neighbors.
   * Ensures all routers remain synchronized.

2. **Triggered Update:**

   * Sent **immediately** when there is a **topology change** (e.g., link failure).
   * Helps routers **converge faster**.

---

## **7. Failure Detection and Convergence**

* Failure is detected using:

  1. **Control packets (Hello/ACK)** – if no ACK, link is assumed down.
  2. **Missed periodic updates** – if a router fails to receive updates within **180 seconds**, it marks the route as unreachable.
* After detecting failure, routers **recalculate** shortest paths and update neighbors.

---

## **8. Count-to-Infinity Problem**

### **Problem:**

* When a link fails, routers may **incorrectly increment hop counts** indefinitely before realizing the destination is unreachable.

### **Example:**

* If link between **F and G** fails:

  * F marks G as unreachable.
  * A neighbor (A) may still advertise a route to G via F.
  * F updates its table to reach G via A (cost increases).
  * This loop continues — hop count keeps increasing until 16 (infinity).

---

### **Solutions to Count-to-Infinity Problem:**

1. **Maximum Hop Count = 15**

   * Routes beyond 15 hops are considered unreachable.

2. **Split Horizon:**

   * A router **does not advertise** a route back to the interface from which it was learned.

3. **Split Horizon with Poisoned Reverse:**

   * A router advertises the failed route to the neighbor with an **infinite metric** (hop count = 16).

4. **Triggered Updates:**

   * Sends updates immediately when a route becomes invalid.

---

## **9. RIP Packet Format**

| **Field**          | **Description**             |
| ------------------ | --------------------------- |
| **Command**        | 1 = Request, 2 = Response   |
| **Version**        | RIP version (v1 or v2)      |
| **Address Family** | Type of network (IP = 2)    |
| **IP Address**     | Destination network address |
| **Metric**         | Number of hops (1–15)       |

* RIP packets are sent using **UDP port 520**.
* Routers **exchange tables every 30 seconds**.

---

## **10. Advantages of Distance Vector (RIP)**

* **Simple** to configure and understand.
* **Low overhead** and suitable for **small networks**.
* Automatically **detects topology changes**.

---

## **11. Disadvantages**

* **Slow convergence** (takes time after topology changes).
* **Count-to-infinity** problem.
* **Scalability limit** (max 15 hops).
* Consumes **more bandwidth** due to periodic updates.

---

## **12. Diagram: RIP Working**

```
      +---------+         +---------+         +---------+
      | Router A|---------| Router B|---------| Router C|
      +---------+         +---------+         +---------+
         |                     |                   |
   Knows only own net    Exchanges tables     Learns paths
   Periodically updates   with neighbors       via updates
```

Each router exchanges distance vectors with its neighbors until all tables stabilize.

---

## ✅ **13. Summary (15-Mark Answer)**

* **RIP** is a simple **distance vector protocol** based on the **Bellman-Ford algorithm**.
* Routers share routing tables periodically with **neighbors only**.
* Metric = **Hop count**; maximum = **15**.
* Handles topology changes via **periodic** and **triggered updates**.
* Problems like **count-to-infinity** are minimized using **split horizon** and **poisoned reverse**.
* Suitable for **small, stable networks** due to its simplicity and limited scalability.
