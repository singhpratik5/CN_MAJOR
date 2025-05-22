# Minor 1 Solutions - Computer Networks

## Q1. OSI Layers vs. TCP/IP Model
- **OSI Model Layers (bottom to top):**
  1. Physical
  2. Data Link
  3. Network
  4. Transport
  5. Session
  6. Presentation
  7. Application
- **TCP/IP Model Layers:**
  1. Network Interface (Physical + Data Link)
  2. Internet (Network)
  3. Transport
  4. Application (Session + Presentation + Application)
- **Missing Layers in TCP/IP:** Session, Presentation
- **Functions of Missing Layers:**
  - Session: Manages sessions/connections
  - Presentation: Data translation, encryption, compression
- **Why combined in TCP/IP?** Simpler, most applications handle these functions themselves.

---

## Q2. Modulation Types (A, B, C)
- **A:** Amplitude Modulation (AM) – amplitude varies, frequency/phase constant
- **B:** Frequency Modulation (FM) – frequency varies, amplitude/phase constant
- **C:** Phase Modulation (PM) – phase varies, amplitude/frequency constant
- **Justification:**
  - AM: Envelope (outline) changes
  - FM: Spacing between cycles changes
  - PM: Sudden phase shifts
- **Carrier Frequency:** The base frequency of the unmodulated carrier
- **Modulating Frequencies:** Number of distinct patterns in the envelope or frequency/phase changes
- **Equations:**
  - AM: s(t) = [Ac + m(t)] × cos(2πfct)
  - FM: s(t) = Ac × cos[2πfct + 2πkf × ∫m(τ)dτ]
  - PM: s(t) = Ac × cos[2πfct + kp × m(t)]

---

## Q3. ADSL in Home Networking
- **ADSL:** Asymmetric Digital Subscriber Line
- **Use:** Provides high-speed internet over telephone lines; more bandwidth for download than upload
- **Home Networking:**
  - ADSL modem connects to telephone line
  - Splitter separates voice and data
  - Modem connects to router/computer
- **Diagram (text):**
  [Internet]---[ADSL Modem]---[WiFi Router]---(PC/Phone)

---

## Q4. Circuit, Message, and Packet Switching
- **Circuit Switching:** Dedicated path for entire session (e.g., telephone)
- **Message Switching:** Entire message stored and forwarded (store-and-forward, high delay)
- **Packet Switching:** Data split into packets, each routed independently (e.g., Internet)
- **Examples:**
  - Circuit: Phone call
  - Message: Telegraph
  - Packet: Email, web browsing

---

## Q5. TDM, FDM, WDM, and Statistical Multiplexing
- **Time Division Multiplexing (TDM):**
  - Each signal gets a time slot
  - Example: Digital telephony
- **Frequency Division Multiplexing (FDM):**
  - Each signal gets a frequency band
  - Example: Radio broadcasting
- **Wavelength Division Multiplexing (WDM):**
  - Each signal gets a light wavelength (fiber optics)
  - Example: Optical networks
- **Statistical Multiplexing:**
  - Bandwidth shared dynamically based on demand
  - High utilization, efficient for bursty traffic

---

## Q6. Ethernet Frame Format
- **Fields:**
  - Preamble: Synchronization
  - SFD: Start Frame Delimiter
  - Destination Address: Receiver's MAC
  - Source Address: Sender's MAC
  - Length: Length of data
  - Data: Actual payload
  - CRC: Error checking
- **CRC Polynomial:** Commonly used: x^32 + x^26 + ... + x + 1 (for Ethernet)

---

## Q7. MAC Layer
- **MAC:** Media Access Control
- **Purpose:** Controls access to the shared medium (who can transmit when)
- **Is it a layer?** Sub-layer of Data Link Layer
- **Number assignment:** Each device gets a unique 48-bit MAC address
- **Ethernet:** Uses CSMA/CD
- **WiFi:** Uses CSMA/CA

---

## Q8. CRC Calculation Example
- **Given Polynomial:** x^5 + x^4 + x^2 + 1
- **Data:** 1010001101
- **Steps:**
  1. Append 5 zeros to data (since highest degree is 5): 101000110100000
  2. Divide by polynomial (binary division)
  3. Remainder is the CRC
- **Work out all steps:**
  - (Show binary long division; final remainder is the answer) 