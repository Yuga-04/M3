

## TCP Congestion Control – 3 Mechanisms

**Definition:**
Congestion control in TCP prevents network overload by regulating how much data a sender can transmit before receiving an acknowledgment.

**Purpose:**
To ensure **efficient data transmission**, avoid **packet loss**, and maintain **network stability**.

---

### 1. **Additive Increase / Multiplicative Decrease (AIMD)**

* TCP maintains a **Congestion Window (CWND)** to limit unacknowledged data in transit.
* **Effective Window:**
  [
  \text{Effective Window} = \min(\text{CWND}, \text{Advertised Window}) - (\text{LastByteSent} - \text{LastByteAcked})
  ]

**Mechanism:**

* **Multiplicative Decrease:** On **timeout**, CWND is halved (e.g., 16 → 8 → 4 → 2 → 1).
* **Additive Increase:** On successful ACKs, CWND increases gradually:
  [
  \text{Increment} = \text{MSS} \times \left( \frac{\text{MSS}}{\text{CWND}} \right)
  ]

**Example:**
If CWND = 16 packets and a loss occurs, CWND → 8. On each ACK, CWND increases fractionally until full recovery.

---

### 2. **Timeout-Based Retransmission**

* TCP uses a **Retransmission Timeout (RTO)** to detect lost segments.
* If an ACK is not received before the RTO expires, TCP **retransmits** the segment at the front of the queue.

**Example:**
A segment with sequence number **1000** is sent. If no ACK arrives within the RTO, TCP retransmits it.

---

### 3. **Fast Retransmission (Three Duplicate ACKs)**

* If TCP receives **three duplicate ACKs** for the same segment, it assumes that segment was lost and **retransmits immediately**, without waiting for the timeout.

**Example:**
Segment **1000** sent → ACK for **1001** received three times → TCP retransmits **segment 1000** instantly.

---

**Summary:**
These mechanisms—**AIMD**, **Timeout-Based Retransmission**, and **Fast Retransmission**—work together to ensure TCP adapts dynamically to network conditions, minimizes congestion, and maintains reliable data delivery.

