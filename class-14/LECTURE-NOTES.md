# Lecture Notes: Intrusion Detection and Prevention Systems (IDS/IPS)

## Review: Ops Challenge Class 11

- What are FIN and RST packets?
  - While coding in how to terminate a connection during the three way hand shake, students will face a decision of using 'F' for FIN or 'R' for RST.
  - Referring to [TCP FIN VS RST Packets- Know the Difference](https://ipwithease.com/tcp-fin-vs-rst-packets/), discuss:
    - TCP `FIN` and `RST` are two ways to terminate a TCP connection.
    - `RST` packets are like forcefully hanging up a telephone call.
    - `FIN` packets are like saying your goodbyes and letting the conversation gradually unwind.

## Lecture: IDS/IPS

- **Why** (5 min)
- Why use IDS, IPS, or HIDS?
  - Detect and/or prevent intrusions in real time on a network
  - Allows defenders to customize defensive detection rules

- **What** (10 min)
- What is IDS/IPS?

  > Be sure to clarify that an IDS watches and establishes baseline network behavior before observing and reporting suspicious network activities. The IPS instead acts like a firewall and attempts to block the activity altogether after the intrusion crosses the firewall.

  - Network intrusion detection system (NIDS)
    - A **NIDS** is a detective security control that finds intruder activity on the network and raises alerts when suspicious traffic is captured using rule sets.
    - Also commonly referred to broadly as IDS.
    - Often included on the perimeter firewall UTM device
  - Network intrusion prevention system (NIPS)
    - A **NIPS** is same as IDS but also detects and actively prevents intrusion.
    - Also commonly referred to broadly as IPS.
  - Types
    - Behavioral
    - Signature-based

- What is Snort?
  - **Snort** is an open source NIPS, capable of performing real-time traffic analysis and packet logging on IP networks. It can perform protocol analysis, content searching/matching, and can be used to detect a variety of attacks and probes, such as buffer overflows, stealth port scans, CGI attacks, SMB probes, OS fingerprinting attempts, and much more.

- What is HIDS?
  - A **host-based intrusion detection system (HIDS)** is an IDS capable of monitoring and analyzing the internals of a computing system as well as the network packets on its network interfaces.
  - Ideally deployed in conjunction with a NIDS to capture traffic that slipped past the NIDS
  - Example: OSSEC
    - Open source HIDS
    - Log-based IDS
    - Rootkit and malware detection
    - Active response
    - Compliance auditing
    - File integrity monitoring
    - System inventory

- **How** (30 min)
  - Ref [DEMO.md](DEMO.md)
