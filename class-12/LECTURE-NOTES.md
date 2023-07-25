# Lecture Notes: Log Analysis with Splunk

## Log Analysis

- **Why** (5 min)
  - Why is log analysis important?
    - Piece together events that already took place 
    - Usable for threat hunting (proactively looking for threats)
    - If maintained properly, admissible as legal evidence  
  - What are we discussing today?
    - Core concepts necessary to complete today's lab, a BOTS workshop

- **What** (10 min)
  - An **advanced persistent threat (APT)** is “a skilled and determined cyber criminal [who] can use multiple vectors and entry points to navigate around defenses, breach your network in minutes and evade detection for months. APTs present a challenge for organizational cyber security efforts.” -FireEye
  - **Web site defacement** is typically a form of hacktivism, where the attacker infiltrates a web server and alters the front page to send a message
  - A **hacktivist** uses offensive security skills to influence policy and attempt to bring about social change
    - Example: Anonymous, a decentralized international activist/hacktivist movement
  - What is the Cyber Kill Chain?
    - A **cyber kill chain** is a security model outlining the sequential phases of a cyber attack
    - Used by defenders to plan ways to interrupt or “break” the cyber kill chain and hopefully thwart the attack entirely
    - Originally developed by Lockheed Martin
    - Today’s lab will be structured around the sequential phases of a cyber kill chain
      - Stages of the Lockheed Martin Cyber Kill Chain:
        - Reconnaissance
        - Weaponization
        - Delivery
        - Exploitation
        - Installation
        - Command and Control
        - Actions on Objectives
  - What is the `metadata` command and how does it work? ([Documentation](https://docs.splunk.com/Documentation/Splunk/latest/SearchReference/Metadata))
    - The `metadata` command returns a list of sources, sourcetypes, or hosts from a specified index or distributed search peer. The metadata command returns information accumulated over time. You can view a snapshot of an index over a specific timeframe, such as the last 7 days, by using the time range picker.
    - Syntax
      - `| metadata type=<metadata-type> [<index-specifier>]... [splunk_server=<wc-string>] [splunk_server_group=<wc-string>]...`
    - Example
      - `| metadata type=hosts`
  - What is a web vulnerability scanner?
    - **Web vulnerability scanners** are automated tools that scan web applications to look for security vulnerabilities such as cross-site scripting (XSS), SQL injection (SQLi), and cross-site request forgery (CSRF).
  - We can use open source intelligence (OSINT) resources to help us analyze the data that we find in our logs.
    - [Threatminer](https://www.threatminer.org/)
    - [VirustTotal](https://www.virustotal.com/gui/)
    - [HybridAnalysis](https://www.hybrid-analysis.com/)
  - What is Dynamic DNS?
    - **Dynamic DNS (DDNS)** is a service that automatically updates a DNS with a web property's correct IP, even if that IP address changes.

- **How** (30 min)
  - Ref. [DEMO.md](DEMO.md)
