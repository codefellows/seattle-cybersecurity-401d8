# Lecture Notes: Traffic Sniffing with Ettercap

## Topic 1

**Why** (5 min)

- Why is sniffing useful for an attacker?
  - Information gathering
  - Ideal - Gather admin credentials

**What** (10 min)

- What is sniffing?
  - Sniffing
    - Active
    - Passive
      - Performed on a hub
      - Must be on same subnet
  - Sniffing tools and techniques
    - Techniques
    - Tools
      - Wireshark
      - tcpdump
      - Burp Suite Proxy
        - Captures HTTP methods
  - Man-in-the-middle (MITM) attack
    - Sniffing data packets between two devices
- What is Ettercap?
  - Comprehensive toolkit for man-in-the-middle attacks.
  - Main features
    - Sniffing of live connections
    - Content filtering
    - Active & passive protocol dissection
    - Network and host analysis capabilities
  - Sniffing tool has two modes
    - UNIFIED (default) Sniffs packets that pass through a single interface.
    - BRIDGED, it uses two network interfaces and forward the traffic from one to the other while performing sniffing and content filtering. This sniffing method is totally stealthy since there is no way to find that someone is in the middle on the cable. You can look at this method as an "on-path" (fka: MITM) attack at layer 1. You will be in the middle of the cable between two entities.

- What is ARP poisoning?
  - Address resolution protocol poisoning
  - Attacker changes a MAC address associated with the impersonated IP by altering targeted computer's ARP cache with a forged ARP request and reply message
  - DO: Draw this out and explain, then quickly demonstrated a successfully poisoned victim PC ARP cache versus a healthy ARP cache
- What is ARP spoofing?
- What is DNS cache poisoning?
