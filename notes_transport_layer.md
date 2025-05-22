# Transport Layer - Exam Notes (Detailed)

## 1. Overview
- The Transport Layer provides end-to-end communication, reliability, flow control, and multiplexing.
- Main protocols: TCP (reliable, connection-oriented), UDP (unreliable, connectionless).

## 2. Key Protocols and Concepts

### 2.1 UDP (User Datagram Protocol)
- **Connectionless, no reliability, no flow control.**
- Used for fast, real-time applications (e.g., video streaming, VoIP).
- **Header fields:** Source port, destination port, length, checksum.
- **Multiplexing/Demultiplexing:** Uses port numbers to distinguish multiple connections on the same host.

### 2.2 TCP (Transmission Control Protocol)
- **Connection-oriented, reliable, provides flow and congestion control.**
- **Key Features:**
  - Sliding window protocol for flow control.
  - Connection establishment (3-way handshake):
    - SYN → SYN-ACK → ACK
    - Diagram (text):
      - Client: SYN →
      - Server:    ← SYN-ACK
      - Client: ACK →
  - Connection termination: FIN and ACK exchange.
  - Reliability: Cumulative and delayed acknowledgements, retransmissions.
  - Sequence numbers and ACKs ensure in-order delivery.
  - **Nagle Algorithm:** Reduces small packet transmission by combining data.
  - **Karn's Algorithm:** Improves RTT estimation by ignoring retransmitted segments.
  - **Congestion Control:**
    - Slow Start, Congestion Avoidance, Fast Retransmit, Fast Recovery.
    - Window size increases exponentially (slow start), then linearly (congestion avoidance).
    - On packet loss, window size is reduced.
  - **RTT (Round Trip Time):** Time for a segment to go to the receiver and back.
    - **RTT Estimation Formula:**
      - EstimatedRTT = (1 - α) × EstimatedRTT + α × SampleRTT
      - Typical α = 0.125

### 2.3 Sliding Window Protocol
- Allows multiple frames to be sent before needing an ACK.
- **Window size** determines how many unacknowledged frames can be in transit.
- **Go-Back-N and Selective Repeat:**
  - Go-Back-N: On error, retransmit from error frame onward.
  - Selective Repeat: Only retransmit erroneous frames.

## 3. Example Questions
1. Explain the TCP 3-way handshake with a diagram.
2. How does TCP ensure reliable data transfer? List mechanisms.
3. Describe the sliding window protocol and its advantages.
4. What is the purpose of Karn's algorithm? How does it improve RTT estimation?
5. Compare UDP and TCP with examples.
6. Explain congestion control in TCP with a window size diagram.

## 4. Exam Tips
- Draw diagrams for sliding window, handshake, and congestion control.
- Be able to explain algorithms step-by-step.
- Use real-world examples (e.g., video streaming for UDP, file transfer for TCP).
- Practice RTT and window size calculation problems. 