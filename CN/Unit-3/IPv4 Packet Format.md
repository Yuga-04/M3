## **IPv4 Packet Format**

An IPv4 datagram is divided into two parts: **Header** and **Data (Payload)**.
The **header** is usually **20–60 bytes** long and contains important control information.

### **Structure of IPv4 Header (20 bytes minimum)**

| Field                     | Size (bits) | Description                                                           |
| ------------------------- | ----------- | --------------------------------------------------------------------- |
| **Version**               | 4           | IP version number (4 for IPv4).                                       |
| **Header Length (IHL)**   | 4           | Length of header in 32-bit words (minimum 5).                         |
| **Type of Service (TOS)** | 8           | Defines priority or quality of service.                               |
| **Total Length**          | 16          | Entire datagram length (header + data) in bytes.                      |
| **Identification**        | 16          | Unique ID assigned to each datagram for fragmentation and reassembly. |
| **Flags**                 | 3           | Control bits — indicate whether fragmentation is allowed.             |
| **Fragment Offset**       | 13          | Shows the position of a fragment in the original datagram.            |
| **Time to Live (TTL)**    | 8           | Limits lifetime of packet; decremented at each router.                |
| **Protocol**              | 8           | Indicates higher-layer protocol (e.g., TCP = 6, UDP = 17).            |
| **Header Checksum**       | 16          | Error-checking code for header.                                       |
| **Source Address**        | 32          | IP address of sender.                                                 |
| **Destination Address**   | 32          | IP address of receiver.                                               |
| **Options (optional)**    | Variable    | Used for testing, security, routing, etc.                             |
| **Padding**               | Variable    | Ensures header ends on a 32-bit boundary.                             |

**Note:** Data portion follows the header and carries transport-layer segments (TCP/UDP).

---

## **Fragmentation in Datagram Delivery**

Since each network may support different **Maximum Transmission Units (MTUs)**, a large IP packet may need to be **fragmented** to fit into smaller frames.

### **When Fragmentation Occurs**

* If an IP datagram is **larger than the MTU** of the network it must pass through.
* Routers may **break the datagram into smaller fragments** that can traverse the link.

### **How Fragmentation Works**

Each fragment:

1. Gets its **own header** (copied from the original).
2. Uses the same **Identification** value.
3. **Flags** and **Fragment Offset** fields indicate fragment details.

#### **Fields Involved**

* **Identification:** Same for all fragments of the original datagram.
* **Flags:**

  * **Bit 0:** Reserved.
  * **Bit 1 (DF – Don’t Fragment):** 1 → do not fragment.
  * **Bit 2 (MF – More Fragments):** 1 → more fragments follow, 0 → last fragment.
* **Fragment Offset:** Indicates position of fragment’s data (in 8-byte units).

---

### **Example**

Suppose a 4000-byte datagram (20-byte header + 3980 bytes data) must pass through a link with **MTU = 1500 bytes**.

* Each fragment can carry **1480 bytes of data (1500 - 20)**.
* Fragments created:

  1. Fragment 1 → Data 0–1479 bytes, **Offset = 0**, **MF = 1**
  2. Fragment 2 → Data 1480–2959 bytes, **Offset = 185 (1480/8)**, **MF = 1**
  3. Fragment 3 → Data 2960–3979 bytes, **Offset = 370 (2960/8)**, **MF = 0**

Receiver reassembles fragments using **Identification**, **Offset**, and **MF**.

---

### **Reassembly**

* Done **only at the destination host**.
* Fragments are arranged using **Fragment Offset**.
* Datagram is accepted when **all fragments are received**.

---

### **Advantages of Fragmentation**

* Enables IP to run over networks with varying MTUs.
* Makes IP flexible and adaptable.

### **Disadvantages**

* Increases overhead (extra headers).
* Higher reassembly time and error probability.

---

### **Diagram (for exam)**

```
 ---------------------------------------------------------------
|Version|IHL|TOS|Total Length|Identification|Flags|Fragment Off|
| TTL | Protocol | Header Checksum | Source IP Address         |
| Destination IP Address                              |
| Options (if any)                                    |
|---------------------------------------------------------------|
| Data (Payload)                                      |
 ---------------------------------------------------------------
```

---

✅ **Summary (for 13 marks)**

* IPv4 header: 20–60 bytes with essential control fields.
* Fragmentation allows datagrams larger than MTU to be split.
* Identification, Flags, and Offset help in reassembly at destination.
* Final packet is reconstructed using all fragments.
