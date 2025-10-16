# 🌐 **Inter-Domain Routing – Border Gateway Protocol (BGP)**

*(15 Marks Answer)*

---

## **1. Introduction**

* The Internet is made up of thousands of **Autonomous Systems (AS)** — networks operated by different organizations (e.g., ISPs, companies, universities).
* **Inter-Domain Routing** is the process of routing **between** these autonomous systems.
* The protocol used for this purpose is the **Border Gateway Protocol (BGP)**.
* It is the **de facto standard** for routing between Internet service providers and large networks.

---

## **2. Need for Inter-Domain Routing**

Routing in the Internet is divided into two types:

1. **Intra-domain routing (Interior Routing)** – Routing **within** an AS.

   * Protocols used: **RIP**, **OSPF**, **IS-IS**.
2. **Inter-domain routing (Exterior Routing)** – Routing **between** ASes.

   * Protocol used: **BGP (Border Gateway Protocol)**.

Because each AS has its own **policies**, **topology**, and **routing metrics**, a specialized routing protocol is required that:

* Can **enforce routing policies**,
* **Prevent loops**, and
* **Scale** to the global Internet.

---

## **3. Autonomous System (AS)**

An **Autonomous System (AS)** is a collection of routers under a **single administrative control** (e.g., an ISP or organization).

Each AS is assigned a unique **AS Number (ASN)** by IANA.

### **Types of Autonomous Systems:**

| **Type**          | **Description**                                                        | **Example**                 |
| ----------------- | ---------------------------------------------------------------------- | --------------------------- |
| **Stub AS**       | Connected to only one AS; carries only local traffic.                  | A small company’s network.  |
| **Multihomed AS** | Connected to multiple ASes but does not carry transit traffic.         | Large enterprise network.   |
| **Transit AS**    | Connected to multiple ASes and carries both local and transit traffic. | Internet backbone provider. |

---

## **4. Challenges in Inter-Domain Routing**

1. **Scale:**

   * The Internet has **hundreds of thousands of networks**.
   * Routers must handle **very large routing tables**.

2. **Policy:**

   * Each AS follows its own routing policy.
   * Example:
     “Prefer ISP-A for outgoing traffic but use ISP-B as backup.”

3. **Trust and Security:**

   * Routers in one AS **must not blindly trust** advertisements from other ASes.
   * Misconfiguration or malicious routes can cause **global routing problems**.

4. **Loop Prevention:**

   * Since there’s no central control, **routing loops** must be avoided.

---

## **5. Basics of BGP**

* **BGP (Border Gateway Protocol)** is an **Exterior Gateway Protocol (EGP)**.
* Current version: **BGP-4** (supports CIDR and Classless routing).
* Runs **over TCP (port 179)** to ensure reliable message delivery.
* Each AS designates one or more routers as **BGP Speakers** (border routers).

### **Working Principle:**

* BGP routers exchange information about **which networks** they can reach, along with the **AS path** to those networks.
* These routes are then propagated to other ASes following routing policies.

---

## **6. BGP Routing Algorithm (Path Vector Protocol)**

* BGP is a **Path Vector Routing Protocol**, which is an extension of Distance Vector Routing.
* Instead of advertising only the distance, each BGP router advertises the **entire path** (list of AS numbers) to reach a destination.

### **How it works:**

1. Each BGP speaker advertises reachable networks to neighboring ASes.
2. Advertisement includes a **path vector** (the sequence of ASes).
3. When a router receives an update, it:

   * **Checks for loops** (if its own AS number appears in the path, it rejects it).
   * **Applies local routing policies** (prefers or rejects certain paths).
4. Chooses the **best path** based on:

   * Shortest AS path
   * Routing policy preferences
   * Next-hop reachability
5. The chosen route is **advertised** to neighboring ASes.

---

### **Example:**

```
       +-----------+           +-----------+
       |   AS 1    |-----------|   AS 2    |
       +-----------+           +-----------+
             |                        |
             |                        |
       +-----------+           +-----------+
       |   AS 3    |-----------|   AS 4    |
       +-----------+           +-----------+
```

* Suppose **AS1** advertises network **128.96.0.0**.
* AS2 learns this and advertises to AS3 with **path (AS2, AS1)**.
* AS3 advertises to AS4 with **path (AS3, AS2, AS1)**.
* If AS1 later receives this advertisement back, it detects its own AS number in the path — hence **loop prevented**.

---

## **7. BGP Message Types**

| **Message Type** | **Purpose**                                           |
| ---------------- | ----------------------------------------------------- |
| **OPEN**         | Establishes a session between BGP peers.              |
| **UPDATE**       | Advertises or withdraws routes.                       |
| **KEEPALIVE**    | Ensures connection is active (sent every 60 seconds). |
| **NOTIFICATION** | Reports errors and closes the session.                |

---

## **8. BGP Route Selection Criteria**

BGP selects the **best route** based on the following attributes:

1. **Highest Local Preference**
2. **Shortest AS Path**
3. **Lowest Origin Type**
4. **Lowest Multi-Exit Discriminator (MED)**
5. **Prefer eBGP over iBGP**
6. **Lowest IGP cost to next hop**
7. **Oldest route (stable)**

This ensures **policy-based** and **loop-free routing**.

---

## **9. Advantages of BGP**

* Supports **policy-based routing**.
* **Loop-free routing** using AS path.
* Highly **scalable** for global Internet routing.
* **CIDR support** (reduces routing table size).
* Ensures **reliable updates** using TCP.

---

## **10. Limitations of BGP**

* **Slow convergence** after topology changes.
* **Complex configuration and policies.**
* **No built-in security** (can be attacked by route hijacking).

---

## **11. Summary of Inter-Domain Routing (BGP)**

| **Feature**         | **Description**                             |
| ------------------- | ------------------------------------------- |
| **Protocol Type**   | Path Vector Routing                         |
| **Purpose**         | Routing between Autonomous Systems          |
| **Runs On**         | TCP (Port 179)                              |
| **Loop Prevention** | Uses AS Path vector                         |
| **Routing Policy**  | Supported                                   |
| **Current Version** | BGP-4                                       |
| **Example Use**     | Routing between ISPs or large organizations |

---

## **12. Diagram Summary (Exam-Friendly)**

```
          +--------------------+
          | Autonomous System 1|
          |  (BGP Speaker A)   |
          +---------+----------+
                    |
             BGP Session (TCP)
                    |
          +---------+----------+
          | Autonomous System 2|
          |  (BGP Speaker B)   |
          +--------------------+

BGP speakers exchange reachability information
with AS-PATH and routing policies.
```
