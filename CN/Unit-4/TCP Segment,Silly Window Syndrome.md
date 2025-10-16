
---

## (i) TCP Segment Format

TCP segment = Header + Data  
**Header (20–60 bytes)** includes:

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

TCP ensures reliable, ordered delivery using sequence and acknowledgment numbers, flow control via window size, and error control via checksum.

---

## (ii) Silly Window Syndrome and Avoidance

**Silly Window Syndrome (SWS)**:  
Occurs when sender/receiver handles data inefficiently, causing transmission of **small segments**, reducing network efficiency.

### Sender-Side SWS:
- Caused by slow data generation (e.g., 1 byte)
- TCP sends 41-byte segment (20 IP + 20 TCP + 1 data)
- **Solution**: **Nagle’s Algorithm**  
  - Send first byte immediately  
  - Buffer subsequent data until ACK or full segment  
  - Prevents byte-by-byte transmission

### Receiver-Side SWS:
- Caused by slow data consumption  
- Receiver advertises small window sizes  
- **Solutions**:  
  - **Clark’s Solution**: ACK with zero window until buffer has space for full segment or half-empty  
  - **Delayed ACK**: Wait before acknowledging to allow buffer space

SWS reduces throughput; solutions optimize segment size and buffer usage for efficient TCP communication.

---
