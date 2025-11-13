Here’s a **20-mark detailed answer** on **Flow Control Mechanisms** — covering both **Stop-and-Wait Protocol** and **Sliding Window Protocol** with clear explanation and diagrams (you can redraw them if needed).

---

## **Flow Control Mechanisms**

### **Introduction**

* **Flow control** is a technique used in data communication to ensure that the **sender does not overwhelm the receiver** with too much data at once.
* It manages the rate of data transmission between two nodes so that the receiver’s buffer does not overflow.
* The main goal is **efficient and reliable data transfer**.

There are two major flow control mechanisms:

1. **Stop-and-Wait Protocol**
2. **Sliding Window Protocol**

---

## **i) Stop-and-Wait Protocol**

### **Concept**

* In this method, the sender **transmits one frame at a time** and then **waits for an acknowledgment (ACK)** from the receiver before sending the next frame.
* It ensures that the receiver processes each frame before receiving the next one.

---

### **Working**

1. The sender sends one data frame.
2. The receiver receives it, processes it, and sends an acknowledgment (ACK).
3. The sender waits until the ACK is received.
4. Once ACK is received, the sender sends the next frame.

If the acknowledgment is **not received within a specific timeout period**, the sender **retransmits** the same frame (assuming it was lost or damaged).

---

### **Advantages**

* Simple to implement.
* Suitable for **reliable links** with **low error rates** and **short propagation delays**.

---

### **Disadvantages**

* **Inefficient** for long-distance or high-speed links (because sender waits idle for ACK).
* Wastes bandwidth due to waiting time.

---

### **Diagram**

```
Sender:  |---Frame 1--->|     wait for ACK
Receiver:                |<---ACK 1------|

Sender:  |---Frame 2--->|     wait for ACK
Receiver:                |<---ACK 2------|
```

---

### **Example**

If transmission time = 5 ms and acknowledgment time = 45 ms,
Efficiency = 5 / (5 + 45) = **10% only**.
So, only 10% of link bandwidth is used effectively.

---

## **ii) Sliding Window Protocol**

### **Concept**

* The **Sliding Window Protocol** allows the sender to **send multiple frames before receiving ACKs** for earlier ones.
* It maintains a **window** (a range of sequence numbers) that represents how many frames can be sent **without waiting** for acknowledgment.

---

### **Types of Sliding Window Protocols**

1. **Go-Back-N ARQ (Automatic Repeat Request)**
2. **Selective Repeat ARQ**

---

### **Working**

1. **Sender Window:**

   * Contains sequence numbers of frames the sender can transmit before an acknowledgment is received.
   * When an ACK is received, the window “slides” forward.

2. **Receiver Window:**

   * Indicates which frames can be accepted.
   * Depending on the protocol type, the receiver may accept frames in or out of order.

---

### **1. Go-Back-N ARQ**

* Sender can send **up to N frames** before waiting for acknowledgment.
* If an error occurs in a frame, all subsequent frames are **resent** from the erroneous frame onwards.

**Example:**
If frame 3 is lost, frames 4, 5, and 6 (already sent) are **discarded** by the receiver and **retransmitted** by the sender.

**Diagram:**

```
Sender:  [0][1][2][3][4] -> Send up to N frames
Receiver: Sends ACK cumulatively (e.g., ACK 3 means 0,1,2 received)
```

---

### **2. Selective Repeat ARQ**

* The receiver **acknowledges each frame individually**.
* Only the **damaged or lost frames** are retransmitted.
* This is **more efficient** than Go-Back-N but more complex.

**Example:**
If frame 3 is lost, the receiver keeps frames 4 and 5 and only requests retransmission of frame 3.

**Diagram:**

```
Sender Window: [0][1][2][3][4]
Receiver Window: [0][1][2][3][4]
ACKs sent individually for each frame.
```

---

### **Advantages**

* Better **channel utilization**.
* Allows **pipelining** (sending multiple frames without waiting).
* Efficient for **high-speed** and **long-delay** networks.

---

### **Disadvantages**

* Requires **more memory** and **complex logic** to maintain windows.
* Error recovery is more complex than Stop-and-Wait.

---

## **Comparison: Stop-and-Wait vs Sliding Window**

| Feature                | Stop-and-Wait   | Sliding Window   |
| ---------------------- | --------------- | ---------------- |
| Frames sent before ACK | 1               | Multiple         |
| Efficiency             | Low             | High             |
| Suitable for           | Low-speed links | High-speed links |
| Complexity             | Simple          | Complex          |
| Bandwidth utilization  | Poor            | Good             |

---

## **Conclusion**

* **Stop-and-Wait Protocol** is simple but inefficient for large networks.
* **Sliding Window Protocol** (especially Selective Repeat ARQ) offers **higher efficiency** and **better utilization** of network resources.
* Hence, most modern reliable communication systems (like TCP) use the **sliding window mechanism** for flow control.

---

✅ **Marking Split (20 Marks):**

* Introduction: 2 marks
* Stop-and-Wait explanation + diagram: 6 marks
* Sliding Window explanation + types + diagram: 8 marks
* Comparison & conclusion: 4 marks

---

Would you like me to include **Tamil explanation** alongside the English one (for easier understanding)?
