
---

## (i) TCP Segment Format

**Definition**:  
A TCP segment is the basic unit of data transmission in TCP, consisting of a **header (20–60 bytes)** and **data**.

**Purpose**:  
To ensure **reliable, ordered, and error-checked delivery** of data between processes over a network.

**Header Fields**:
- **Source Port (16 bits)**: Sender’s application port  
- **Destination Port (16 bits)**: Receiver’s application port  
- **Sequence Number (32 bits)**: First byte’s number in segment  
- **Acknowledgment Number (32 bits)**: Next expected byte  
- **Header Length (4 bits)**: Size of header (5–15 words)  
- **Control Flags (6 bits)**: URG, ACK, PSH, RST, SYN, FIN  
- **Window Size (16 bits)**: Flow control from receiver  
- **Checksum (16 bits)**: Mandatory error detection  
- **Urgent Pointer (16 bits)**: Valid if URG flag is set  
- **Options & Padding (0–40 bytes)**: Optional info

**Functionality**:
- Enables **full-duplex**, **process-to-process** communication  
- Supports **flow control**, **error control**, and **connection management**  
- Uses **sequence and acknowledgment numbers** for reliability

---

## (ii) Silly Window Syndrome

**Definition**:  
Silly Window Syndrome (SWS) is a TCP inefficiency where **small segments** are transmitted due to slow data generation or consumption.

**Purpose of Avoidance**:  
To **maximize network efficiency** by preventing transmission of small, wasteful segments.

### Sender-Side SWS:
- Caused by slow application generating small data (e.g., 1 byte)
- TCP sends 41-byte segment (20 IP + 20 TCP + 1 data)
- **Solution**: **Nagle’s Algorithm**  
  - Send first byte immediately  
  - Buffer data until ACK or full segment  
  - Prevents byte-by-byte transmission

### Receiver-Side SWS:
- Caused by slow application consuming data
- Receiver advertises small window sizes
- **Solutions**:  
  - **Clark’s Solution**: ACK with zero window until buffer has space for full segment or half-empty  
  - **Delayed ACK**: Wait before acknowledging to allow buffer space

**Impact**:  
SWS reduces throughput and increases overhead. Solutions ensure **optimal segment size**, **buffer usage**, and **TCP performance**.

---
