# Physical Layer - Exam Notes (Detailed)

## 1. Modulation Techniques

### Amplitude Modulation (AM)
- **Definition:** The amplitude of the carrier signal is varied in proportion to the message (baseband) signal.
- **Formula:**
  - Modulated signal: \( s(t) = [A_c + m(t)] \cos(2\pi f_c t) \)
    - Where \( A_c \) = carrier amplitude, \( m(t) \) = message signal, \( f_c \) = carrier frequency
- **Diagram (text):**
  - Message:      ~~~~~~
  - Carrier:      /\/\/\/\/\
  - AM Output:    /\_/\_/\_/\_
- **Applications:** AM radio broadcasting

### Frequency Modulation (FM)
- **Definition:** The frequency of the carrier signal is varied by the message signal.
- **Formula:**
  - \( s(t) = A_c \cos[2\pi f_c t + 2\pi k_f \int m(\tau) d\tau] \)
    - Where \( k_f \) = frequency sensitivity
- **Advantages:** Less susceptible to noise than AM
- **Applications:** FM radio, audio transmission

### Phase Modulation (PM)
- **Definition:** The phase of the carrier signal is varied by the message signal.
- **Formula:**
  - \( s(t) = A_c \cos[2\pi f_c t + k_p m(t)] \)
    - Where \( k_p \) = phase sensitivity
- **Applications:** Used in digital modulation schemes (e.g., PSK)

### ADSL (Asymmetric Digital Subscriber Line)
- **Definition:** Uses different frequencies for upstream and downstream data over telephone lines.
- **Application:** Broadband internet access

## 2. Multiplexing Techniques

### Frequency Division Multiplexing (FDM)
- **Definition:** Multiple signals are transmitted simultaneously on different frequency bands.
- **Diagram (text):**
  - |---Signal 1---|---Signal 2---|---Signal 3---|
  - Each occupies a unique frequency range.
- **Formula:** Bandwidth required = sum of all channel bandwidths + guard bands
- **Applications:** Cable TV, radio broadcasting

### Time Division Multiplexing (TDM)
- **Definition:** Multiple signals share the same channel by taking turns in different time slots.
- **Diagram (text):**
  - |S1|S2|S3|S1|S2|S3| (S = Signal)
- **Types:** Synchronous TDM, Asynchronous TDM
- **Applications:** Digital telephony

### Wavelength Division Multiplexing (WDM)
- **Definition:** Used in fiber optics; different data streams are sent on different light wavelengths.
- **Applications:** Optical fiber communication

### Differential PCM (Pulse Code Modulation)
- **Definition:** Encodes the difference between successive samples for efficient digital transmission.

## 3. Switching Techniques

### Circuit Switching
- **Definition:** Dedicated path established for the entire communication session.
- **Example:** Traditional telephone network
- **Advantage:** Consistent, predictable performance
- **Disadvantage:** Inefficient for bursty data

### Message Switching
- **Definition:** Entire message is stored and forwarded from one node to another.
- **Advantage:** No need for dedicated path
- **Disadvantage:** High delay due to store-and-forward

### Packet Switching
- **Definition:** Data is broken into packets, each routed independently.
- **Example:** Internet
- **Advantage:** Efficient use of network, robust
- **Disadvantage:** Variable delay, possible packet loss

## 4. Important Formulas
- **Nyquist Bit Rate:** \( Bit\ Rate = 2 \times Bandwidth \times \log_2(L) \)
  - Where L = number of signal levels
- **Shannon Capacity:** \( C = B \log_2(1 + S/N) \)
  - Where C = channel capacity, B = bandwidth, S/N = signal-to-noise ratio

## 5. Example Questions
1. Explain and derive the formula for AM and FM. Draw their waveforms.
2. Compare FDM and TDM with diagrams and applications.
3. What is circuit switching? How does it differ from packet switching?
4. Calculate the maximum data rate for a channel with 3 kHz bandwidth and S/N ratio of 30 dB.

## 6. Exam Tips
- Always draw labeled diagrams for modulation and multiplexing.
- Use formulas for numerical questions (e.g., Nyquist, Shannon).
- Compare switching techniques in a table for clarity.
- Use real-world examples for each technique. 