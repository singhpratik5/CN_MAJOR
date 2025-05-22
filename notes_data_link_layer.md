# Data Link Layer - Exam Notes (Detailed)

## 1. Overview
- The Data Link Layer is responsible for node-to-node data transfer, framing, error detection/correction, and flow control.
- It ensures reliable transmission over a physical link.

## 2. Key Protocols and Concepts

### 2.1 PPP (Point-to-Point Protocol) and PPPoE
- **PPP:** Used for direct communication between two nodes (e.g., dial-up).
  - Provides framing, error detection (CRC), authentication (PAP, CHAP).
- **PPPoE:** Encapsulates PPP frames inside Ethernet frames for broadband access.

### 2.2 MAC Layer
- **MAC Address:** 48-bit unique identifier for network interfaces (e.g., 00:1A:2B:3C:4D:5E).
- **Ethernet:**
  - Most common LAN technology.
  - Uses CSMA/CD (Carrier Sense Multiple Access with Collision Detection).
  - **Frame Format:**
    - Preamble | Destination MAC | Source MAC | Type | Data | CRC
  - **Manchester Encoding:**
    - Each bit has a transition in the middle (0 = high-to-low, 1 = low-to-high).
    - Diagram (text):
      - 0: __|‾
      - 1: ‾|__

### 2.3 Switched Ethernet
- Uses switches to forward frames based on MAC addresses, reducing collisions.

### 2.4 VLANs (Virtual LANs)
- **Definition:** Logical segmentation of a physical network into multiple broadcast domains.
- **Benefits:** Improved security, reduced broadcast traffic, easier management.
- **Diagram (text):**
  - [Switch]--(VLAN 10)--[PC1, PC2]
  - [Switch]--(VLAN 20)--[PC3, PC4]

### 2.5 Spanning Tree Protocol (STP)
- **Purpose:** Prevents loops in Ethernet networks by creating a loop-free logical topology.
- **How it works:** Elects a root bridge, disables redundant paths.
- **Diagram (text):**
  - Switch1---Switch2
     |         |
   Switch3----/
  (STP disables one link to prevent loop)

## 3. Error Detection and Correction
- **Parity Bit:** Adds a bit to make the number of 1s even (even parity) or odd (odd parity).
- **Checksum:** Sum of data segments, used in IP, TCP, UDP.
- **CRC (Cyclic Redundancy Check):** Polynomial division, detects burst errors.
- **Hamming Code:** Can detect and correct single-bit errors.

## 4. Framing Methods
- **Character Count:** Frame starts with a count of bytes.
- **Flag Bytes with Byte Stuffing:** Special flag byte marks frame boundaries; escape bytes used if flag appears in data.
- **Bit Stuffing:** Insert extra 0 after five consecutive 1s in data.

## 5. Flow Control
- **Stop-and-Wait:** Sender waits for ACK after each frame.
- **Sliding Window:** Multiple frames sent before needing ACK; window size controls flow.

## 6. Example Questions
1. Explain the working of Ethernet and the role of MAC addresses.
2. What is VLAN and why is it used? Draw a diagram.
3. Describe the Spanning Tree Protocol with a diagram.
4. Explain CRC with an example.
5. Compare Stop-and-Wait and Sliding Window flow control.

## 7. Exam Tips
- Draw diagrams for Ethernet frames, VLANs, and STP.
- Be able to explain Manchester encoding with a waveform diagram.
- Practice CRC and Hamming code error detection/correction problems.
