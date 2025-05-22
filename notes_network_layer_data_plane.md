# Network Layer: Data Plane - Exam Notes (Detailed)

## 1. Overview
- The Network Layer is responsible for routing packets across networks, logical addressing, and fragmentation.
- It provides host-to-host communication.

## 2. Key Concepts and Protocols

### 2.1 IP Addressing
- **IPv4 Address:** 32 bits, written as four decimal numbers (e.g., 192.168.1.1).
- **Subnetting:** Divides a network into smaller subnets. Uses subnet mask (e.g., 255.255.255.0).
- **CIDR (Classless Inter-Domain Routing):**
  - Allows variable-length subnet masks (e.g., 192.168.1.0/24).
  - More efficient use of IP address space than classful addressing.
- **Example:**
  - 192.168.1.0/24 means 24 bits for network, 8 bits for hosts.

### 2.2 Internet Protocol Datagram
- **Structure:**
  - Version | Header Length | Type of Service | Total Length | Identification | Flags | Fragment Offset | TTL | Protocol | Header Checksum | Source IP | Destination IP | Data
- **Fragmentation:**
  - Large packets are split into smaller fragments to fit MTU (Maximum Transmission Unit).
  - Each fragment has offset and more fragments (MF) flag.
- **Reassembly:**
  - Done at the destination using fragment offset and identification fields.

### 2.3 IP Forwarding Algorithm
- Routers use routing tables to forward packets based on destination IP address.
- Longest prefix match is used in CIDR.

### 2.4 ARP (Address Resolution Protocol)
- **Purpose:** Maps IP addresses to MAC addresses in a local network.
- **How it works:**
  - Host broadcasts ARP request for a given IP.
  - Device with matching IP replies with its MAC address.
- **Example:**
  - Host A wants to send to 192.168.1.2, sends ARP request, Host B replies with its MAC.

### 2.5 ICMP (Internet Control Message Protocol)
- **Purpose:** Used for error reporting and diagnostics (e.g., ping, traceroute).
- **Common Messages:**
  - Echo Request/Reply (ping)
  - Destination Unreachable
  - Time Exceeded
  - Redirect
- **Path MTU Discovery:** Uses ICMP to find the largest packet size that can traverse a path without fragmentation.

## 3. Important Formulas
- **Number of Hosts in a Subnet:**
  - Hosts = 2^(number of host bits) - 2
- **Subnet Mask Calculation:**
  - For /n prefix, subnet mask has n bits set to 1, rest are 0.

## 4. Example Questions
1. Explain the process of IP fragmentation and reassembly with an example.
2. What is CIDR? How does it differ from classful addressing?
3. Describe the working of ARP with a step-by-step example.
4. What are the uses of ICMP? List common message types.
5. Calculate the number of hosts possible in a /27 subnet.

## 5. Exam Tips
- Practice subnetting and CIDR notation problems.
- Draw diagrams for IP datagram structure and fragmentation.
- Know the ICMP message types and their uses.
- Be able to explain ARP and routing table lookups with examples. 