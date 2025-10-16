## Adaptive Retransmission in TCP

**Definition**:  
Adaptive retransmission is a mechanism in TCP that dynamically adjusts the **Retransmission Timeout (RTO)** based on network conditions to ensure **efficient and reliable data delivery**.

**Purpose**:  
To avoid unnecessary retransmissions and reduce congestion by adapting to **varying round-trip times (RTT)** in the network.

---

### Mechanism of Adaptive Retransmission

TCP uses **error control** through:
- **Checksum**: Detects corruption  
- **Acknowledgment (ACK)**: Confirms receipt  
- **Timeout (RTO)**: Triggers retransmission if ACK not received

#### 1. **Retransmission after RTO**
- TCP maintains one **RTO per connection**
- If ACK not received before RTO expires, TCP **resends the segment** with the **smallest sequence number**
- Timer is **restarted** after retransmission

#### 2. **Fast Retransmission (Three Duplicate ACKs)**
- If **three duplicate ACKs** are received for the same segment, TCP **retransmits immediately**
- This avoids waiting for RTO and speeds up recovery
- Known as **fast retransmit**

---

### Example

- Segment with sequence number 1000 is sent  
- If no ACK within RTO → retransmit  
- If ACKs for 1001 arrive thrice → fast retransmit segment 1000

---

**Benefit**:  
Adaptive retransmission improves **TCP efficiency**, reduces **delay**, and maintains **network stability** under dynamic conditions.
