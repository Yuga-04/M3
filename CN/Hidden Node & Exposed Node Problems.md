## IEEE 802.11: Hidden Node & Exposed Node Problems

### 🔹 Definition & Purpose

- **Hidden Node Problem**: Occurs when two nodes (e.g., A and C) are out of each other's range but both transmit to a common receiver (e.g., B), causing collisions at B.
- **Exposed Node Problem**: Happens when a node (e.g., C) refrains from transmitting because it senses another nearby transmission (e.g., B to A), even though its transmission wouldn’t cause interference.

**Purpose of Solutions**:  
To improve **throughput**, **reduce collisions**, and ensure **efficient medium access** in wireless LANs.

---

## 🔹 Solutions in IEEE 802.11

### 1. **Hidden Node Problem – Solved by RTS/CTS Mechanism**

**RTS (Request to Send)** and **CTS (Clear to Send)** are control frames used to reserve the medium before actual data transmission.

**Mechanism**:
- Sender (A) sends **RTS** to receiver (B)
- Receiver (B) replies with **CTS**
- Nodes hearing CTS (e.g., C) defer transmission
- Hidden nodes (like C) that didn’t hear RTS but hear CTS avoid collision

**Example**:
- A → RTS → B  
- B → CTS → A  
- C hears CTS → defers transmission  
- A sends data safely to B

This ensures **collision avoidance** even when nodes are hidden from each other.

---

### 2. **Exposed Node Problem – Solved by MAC Layer Logic**

IEEE 802.11 uses **Carrier Sense Multiple Access with Collision Avoidance (CSMA/CA)** and **physical carrier sensing thresholds** to address exposed node issues.

**Mechanism**:
- Node C senses medium busy due to B’s transmission to A
- But C’s transmission to D wouldn’t interfere
- IEEE 802.11 allows transmission if signal strength is below **carrier sense threshold**
- **MAC layer** ignores weak signals that won’t cause collision

**Example**:
- B → A (C overhears)
- C wants to send to D
- C checks signal strength → below threshold → proceeds with transmission

This avoids **unnecessary deferral**, improving **network utilization**.

---

## 🔹 Summary

| Problem         | Cause                                  | Solution           | Mechanism Used         |
|----------------|-----------------------------------------|--------------------|------------------------|
| Hidden Node     | Nodes out of range, collide at receiver| RTS/CTS handshake  | Control frame exchange |
| Exposed Node    | Node defers unnecessarily              | MAC layer logic    | Signal threshold check |

IEEE 802.11’s **RTS/CTS** and **adaptive sensing** mechanisms ensure **efficient medium access**, solving both problems and enhancing wireless LAN performance.

