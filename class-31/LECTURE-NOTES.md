# Lecture Notes: Threat Hunting with YARA

## Course Overview

## Lecture: Threat Hunting

- **Why** (5 min)

  - Why is threat hunting used?
    - Increasingly popular due to increasing prevalence of APTs
    - Traditional defenses such as firewalls and endpoint AV are not stopping threat actors
      - Instead, threat hunters use a hypothesis-driven approach supported by behavioral analytics
      - Defend from the inside out; assume the adversary is already in your networks
    - Telemetry factor: Important to beat threat actors to the punch by detecting earlier in the process

- **What** (10 min)

  - What is threat hunting?
    - Crowdstrike definition: Threat hunting is the practice of proactively searching for cyber threats that are lurking undetected in a network.
      - Threat hunters know TTPs inside and out because they constantly search for them.
    - Highly knowledgeable of IT environments, malware attack vectors, and threat actors.
    - Not incident responders. They do not perform remediation. Signature characteristic is it's proactive, NOT reactive.

      1. Threat hunting from [SQRRL - The Hunting Loop](https://medium.com/@sqrrldata/the-hunting-loop-10c7d451dec8) article

![threat](../assets/threat-hunt.png)

- Create hypothesis
- Investigate
- Uncover new patterns and TTPs
- Inform and enrich analytics
  - How difficult is it to collect IoCs and how much pain can the IoC inflict on adversaries?
  - Introducing….the Pyramid of Pain!

![pop](../assets/pop.png)

- Incident Detection
  - Indicators of Compromise (IOC)
    - File extensions
    - IP block list
    - Domain block list (DBL)
    - Behavioral detection tools
    - Ransom notes

## Review: Ops Challenge Class 30

- How many detections did your hash/file get on VirusTotal?
- How easy was it to bypass VirusTotal?
  - What does this tell you about anti-malware evasion?

## Threat Hunting with YARA

### Why

- Why should we learn how to write custom malware detection rules?
  - Automation and tuning your defenses
  - Tailor your defenses to the threats observed.
    - "YARA is as smart as you make it." -[Monty St. John](https://cybersecurity.att.com/blogs/security-essentials/explain-yara-rules-to-me)
    - "Fool me once, shame on you. Fool me twice, shame on me." -Randall Terry
      - Remember there's always a learning process in security frameworks. This applies to malware detection efforts as well.
    - Different orgs face different threats.
    - Doesn't only look for malware. Evaluates all kinds of attributes belonging to the file in question.
  - Addresses the gap between product and unique needs of the organization
    - No one-size-fits-all anti-malware solution exists!
    - DO: Draw a Venn diagram of product vs business

- Why should we use an anti-malware solution that supports custom detection rules?
  - Extensibility: "Extensibility is a software engineering and systems design principle that provides for future growth. Extensibility is a measure of the ability to extend a system and the level of effort required to implement the extension." -Wikipedia
  - Organizations grow and mature. So should your security defenses.

### What

- What is YARA?
  - Boolean logic pattern matching system
  - Useful in many scenarios
    - Digital forensics
    - Incident response
    - Reverse engineering
    - Threat hunting
  - Open source
  - Works on many OS
  - Targets files
  - Used in many tools you might not expect
    - SIEM
    - Triage
    - Phishing
    - Sandbox
    - IDS
    - Anti-malware/Antivirus
- What is a YARA rule?
  - Checks whether the target file meets the rule or not
  - Often used to determine whether a file is malicious or not
  - Syntax
    - Strings
      - Hexadecimal
      - Text
      - Regular expressions
    - Conditions
      - Boolean in nature. True/False.
  - Great unique strings and identifier for YARA rules
    - Mutexes
    - Unusual user agents
    - Registry keys
    - PBD paths
    - Encrypted config strings
  - What is ClamAV?
    - Open source anti-malware solution
    - Supports the YARA engine
      - YARA rules can either compliment or replace the ClamAV signatures database
