# Lecture Notes: Threat Hunting with Zeek and RITA

## Review: Lab Class 26

## Review: Op Challenge 26

## Demo: Ops Challenge 27

## Lecture: Threat Hunting with Zeek and RITA

- What is beaconing? [CS](https://askinglot.com/what-is-beaconing-in-cyber-security)
  - Beaconing is when the malware communicates with a C2 server asking for instructions or to exfiltrate collected data on some predetermined asynchronous interval.
  - The C2 server hosts instructions for the malware, which are then executed on the infected machine after the malware checks in.
  - DO: Draw this out as a diagram referencing [hunting](https://www.activecountermeasures.com/blog-beacon-analysis-the-key-to-cyber-threat-hunting/)
  - Key characteristics of a beacon
    - Beacon timing
    - Beacon packet size
  - Beacon false positives WILL occur
  - Proper beacon analysis is a difficult, tedious process
  - Beacon with many connections strobe

- What is RITA?
  - RITA stands for Real Intelligence Threat Analytics.
  - RITA is an open source framework for network traffic analysis.
  - The framework ingests Bro/Zeek Logs in TSV format, and currently supports the following major features:
    - Beaconing Detection: Search for signs of beaconing behavior in and out of your network
    - DNS Tunneling Detection Search for signs of DNS based covert channels
    - Block list Checking: Query block lists to search for suspicious domains and hosts

- What is Zeek? (zeek.org)
  - Open source network security monitoring tool
  - Commonly associated with threat hunting
  - Developed in the 90s originally as Bro

- **How** (30 min)

  - How can we perform threat hunting?
    - We perform threat hunting by analyzing at a deeper level our environment using tools like Zeek, RITA, and Wireshark.
