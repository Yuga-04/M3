

## TCP Congestion Control – 3 Mechanisms

**Definition**:  
Congestion control in TCP prevents network overload by regulating the amount of data a sender can transmit before receiving an acknowledgment.

**Purpose**:  
To ensure **efficient data transmission**, avoid **packet loss**, and maintain **network stability**.

---

### 1. **Additive Increase / Multiplicative Decrease (AIMD)**

- TCP maintains a **Congestion Window (CWND)** to limit unacknowledged data in transit.
- **Effective Window** = min(CWND, Advertised Window) – (LastByteSent – LastByteAcked)

**Mechanism**:
- **Multiplicative Decrease**: On **timeout**, CWND is halved (e.g., 16 → 8 → 4 → 2 → 1)
- **Additive Increase**: On successful ACKs, CWND increases gradually:
  \[
  \text{Increment} = \text{MSS} \times \left(\frac{\text{MSS}}{\text{CWND}}\right)
  \]

**Example**:  
If CWND = 16 packets and a loss occurs, CWND → 8. On each ACK, CWND increases fractionally until full recovery.

---

### 2. **Timeout-Based Retransmission**

- TCP uses **Retransmission Timeout (RTO)** to detect lost segments.
- If ACK not received before RTO expires, TCP **retransmits** the segment at the front of the queue.

**Example**:  
Segment with sequence number 1000 is sent. If no ACK within RTO, it is resent.

---

### 3. **Fast Retransmission (Three Duplicate ACKs)**

- If TCP receives **3 duplicate ACKs** for the same segment, it assumes loss and **retransmits immediately**, without waiting for timeout.

**Example**:  
Segment 1000 sent, ACKs for 1001 received thrice → TCP retransmits segment 1000 instantly.

---

These mechanisms together ensure TCP adapts to network conditions, avoids congestion, and maintains reliable transmission.
