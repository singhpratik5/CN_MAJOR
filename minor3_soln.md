# Minor 3 Solutions - Computer Networks

## 1. UDP as a "No Frills" Transport Layer Service & Multiplexing/Demultiplexing
UDP provides a simple, connectionless service:
- No connection setup, no reliability, no flow control, no congestion control.
- Example: DNS queries use UDP for fast, simple request/response.

**Multiplexing/Demultiplexing:**
- Allows multiple applications to use the network simultaneously.
- Achieved using port numbers.
- Example: Web server (port 80), DNS server (port 53) on the same machine.

---

## 2. TCP Reliability Mechanisms
TCP provides reliable, in-order delivery even if IP is unreliable:
- **Lost Packets:** Detected by missing ACKs; retransmitted.
- **Duplicate Packets:** Sequence numbers ensure duplicates are discarded.
- **Delayed Packets:** Sequence numbers allow correct ordering.
- **Corrupted Packets:** Checksum detects errors; corrupted segments are dropped.
- **Mechanisms:**
  - Sequence numbers, ACKs, retransmissions, checksums, cumulative ACKs, timers, fast retransmit, sliding window.

---

## 3. GBN and SR Protocols, Sequence Number Issues
- **GBN (Go-Back-N):** Sender can send N frames before needing ACK. On error, retransmits from error frame onward.
- **SR (Selective Repeat):** Only erroneous frames are retransmitted.
- **Sequence Number Space:** If window size is too large relative to sequence number space, ambiguity arises (old frames may be mistaken for new).
- **Rule:** Window size ≤ (sequence number space + 1)/2.

---

## 4. TCP RTT Estimation
- **Process:** TCP measures time between sending a segment and receiving its ACK (SampleRTT).
- **EstimatedRTT Formula:**
  EstimatedRTT = (1 - α) × EstimatedRTT + α × SampleRTT (α ≈ 0.125)
- **Why dynamic?** Network conditions change; fixed value can cause premature timeouts or delays.
- **No fixed value:** Because RTT varies due to congestion, routing changes, etc.

---

## 5. TCP Window Size and Congestion
- **Before congestion:** Window size increases (slow start, then congestion avoidance).
- **After congestion:** Window size drops (multiplicative decrease), then increases slowly.
- **Diagram (text):**
  |---/\----/\----/\---| (window size increases, drops on congestion)

---

## 6. DNS Message Format & Types
- **DNS Message Format:** Header | Question | Answer | Authority | Additional
- **TYPE:** Specifies record type (A = IPv4, CNAME = alias, etc.)
- **A record:** Maps name to IPv4 address.
- **CNAME:** Maps name to another canonical name.

---

## 7. DNS Query Resolution
- **Two ways:**
  1. **Recursive:** DNS server queries others on behalf of client.
  2. **Iterative:** DNS server refers client to another server.
- **Example:**
  Client → Local DNS (recursive) → Root → TLD → Authoritative DNS → IP

---

## 8. HTTP Request-Response, Non-Persistent Connections
- **HTTP:** Client sends request, server responds (GET, POST, etc.).
- **Non-persistent:** New TCP connection for each object (HTML, images, etc.).
- **Example:**
  Browser requests HTML, then opens new connections for images.

---

## 9. MIME and SMTP
- **MIME:** Allows email to include text, images, attachments.
- **Importance for SMTP:** SMTP only supports text; MIME enables rich content.
- **Base64:** Yes, MIME uses base64 to encode binary data for email. 