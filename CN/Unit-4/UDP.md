
---

## Definition of UDP

**UDP (User Datagram Protocol)** is a **connectionless**, **unreliable** transport protocol that provides **process-to-process communication** over IP. It adds minimal overhead and is suitable for applications that prioritize speed over reliability.

---

## Operations of UDP

### 1. **User Datagram**
- Fixed-size **8-byte header** with:
  - Source Port (16 bits)
  - Destination Port (16 bits)
  - Total Length (16 bits)
  - Checksum (16 bits)
- Data size: 8 to 65,535 bytes

### 2. **Connectionless Service**
- No connection setup or teardown
- Each datagram is independent and may take different paths

### 3. **Process-to-Process Communication**
- Uses **socket addresses** (IP + port) for end-to-end delivery

### 4. **Flow Control**
- No built-in flow control; receiver may overflow

### 5. **Error Control**
- Only checksum-based; no retransmission or acknowledgment
- Corrupted datagrams are silently discarded

### 6. **Encapsulation/Decapsulation**
- UDP encapsulates data into datagrams and decapsulates at the receiver

### 7. **Multiplexing/Demultiplexing**
- Uses port numbers to handle multiple processes

### 8. **Congestion Control**
- No congestion control; assumes small, sporadic traffic

---

## UDP Checksum

**Purpose**:  
To detect errors in the datagram during transmission.

### Checksum Calculation Includes:
1. **Pseudoheader** (from IP layer):
   - Source IP (32 bits)
   - Destination IP (32 bits)
   - Protocol (8 bits, value = 17 for UDP)
   - UDP Length (16 bits)

2. **UDP Header**  
3. **Data** (padded to multiple of 16 bits)

### Example:

Assume:
- Source IP: `192.168.1.1`
- Destination IP: `192.168.1.2`
- Protocol: `17`
- UDP Length: `32 bytes`
- Data: `"Hello"`

Steps:
- Combine pseudoheader + UDP header + data
- Compute 16-bit one's complement sum
- Take one's complement of the result → **Checksum**

If checksum is **all 0s**, sender may complement again to **all 1s** to indicate checksum is used.

---

**Conclusion**:  
UDP is lightweight and fast, ideal for real-time and low-latency applications. Its checksum mechanism ensures basic error detection, while operations remain minimal for speed.

