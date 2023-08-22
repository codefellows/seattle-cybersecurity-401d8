# Lecture Notes: Malware Traffic Analysis with Wireshark

## Topic Malware Traffic Analysis with Wireshark

### Why (5 min)

- Why perform traffic analysis?
  - Malware incidents leave a bread crumb trail, e.g. logs and packets
  - Use behavior patterns to spot suspicious activities
  - Pinpoint "invisible" threats
  - Minimize damage and profit loss
  - Traffic analysis can have different purposes or contexts. Threat hunting is one context you'd perform traffic analysis in. Today's focus is on capturing malware behavior patterns using traffic analysis tools and techniques.

### What (10 min)

- What is traffic analysis?
  - Network **traffic analysis** is the practice of capturing network packets into a packet capture (PCAP) file, then analyzing that file for useful information.
    - If part of an investigation, packet analysis attempts to answer who, what, when, where, and why.
  - Part of our focus will be on forensics topics this week
  - In many networks this is made possible using traffic mirroring (copying packets and sending them for analysis). AWS, for example, offers cloud-based traffic mirroring for Nitro-based EC2 instances.
  - Many routers (e.g. pfSense) are capable of performing traffic mirroring.
- What is an IOC?
  - **Indicators of compromise (IOC)** are pieces of forensic data that identify potentially malicious activity on a system or network.
    - Can be system log entries, data objects such as malicious system files recovered from a compromised machine, or network traffic indicating suspicious activity on the network.
      - Data objects determined to be IOCs are commonly referred to as **artifacts**.
      - Note that artifacts can be hashed to produce a unique **signature**, which is how signature-based malware detection software is able to determine if a file is malware.
    - IOCs help us answer the question, "What happened?"
    - Identified *after* the attack or incident has taken place.
    - Alerts, system log entries, files
    - IOCs are the "breadcrumbs" that lead to detection
    - Sometimes not the easiest to find
    - Here are some additional IOC examples that you may encounter in field:
      - Unusual Outbound Network Traffic
      - Anomalies in Privileged User Account Activity
      - Geographical Irregularities
      - Log-In Red Flags
      - Increases in Database Read Volume
      - HTML Response Sizes
      - Large Numbers of Requests for the Same File
      - Mismatched Port-Application Traffic
      - Suspicious Registry or System File Changes
      - Unusual DNS Requests
      - Unexpected Patching of Systems
      - Mobile Device Profile Changes
      - Bundles of Data in the Wrong Place
      - Web Traffic with Unhuman Behavior
      - Signs of DDoS Activity
- What is an indicator of attack?
  - An **indicator of attack (IoA)** is similar to an IOC but is a forensic piece of evidence associated with an attack in progress.
  - Answers "What is happening and why?"
- What tools can I use to analyze network traffic?
  - Wireshark
  - Tcpdump
  - Zeek

### Community Projects (Remaining Time)

If you end up with extra time, feel free to delve into some of the community-driven efforts around improving IOC workflow. However, the below topics are not essential for completing today's lab.

- What is OpenIOC? (ref. [SANS](https://www.sans.org/reading-room/whitepapers/forensics/ioc-indicators-compromise-malware-forensics-34200))
  - **OpenIOC** is a framework that attempts to standardize the workflow of reporting IOCs
    - Initial leads
      - IOC Creation
    - Deploy IOC
    - Identify Suspect Systems
    - Preserve/Collect Evidence
    - Analyze Data
- What is CybOX? (ref. [Cyware](https://cyware.com/educational-guides/cyber-threat-intelligence/what-is-cybox-how-do-you-use-a-cybox-object-af90) and [CybOX](https://cybox.mitre.org/about/))
  - **CybOX** is a standardized language for encoding and communicating high-fidelity information about cyber observables.
  - CybOX is to IOC as SQL is to relational database transactions.
