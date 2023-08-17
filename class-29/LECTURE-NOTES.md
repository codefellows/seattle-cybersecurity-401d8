# Lecture Notes: Modeling a Web Application

## Threat Modeling

- **Why** (5 min)
    1. Why use threat modeling (ref. [SecurityIntelligence.com](https://securityintelligence.com/posts/what-is-threat-modeling-and-how-does-it-impact-application-security/))?
       1. Cyber education and awareness
       1. Create teachable moments for non-security teams to gain awareness
       1. Improve application security posture
       1. Fundamental to DevSecOps

- **What** (10 min)
    1. What is threat modeling (ref. [SecurityIntelligence.com](https://securityintelligence.com/posts/what-is-threat-modeling-and-how-does-it-impact-application-security/))?
      1. Threat modeling is the practice of identifying and prioritizing potential threats and security mitigations to protect something of value, such as confidential data or intellectual property. By continuously threat modeling applications, security teams can better protect apps while educating the development team and building a culture of security throughout the enterprise.

- **How** (30 min)
- **Experimentation and Discovery Ideas**

## Threat Classification with STRIDE

- **Why**

- Why use STRIDE?
  - As part of threat modeling, we should be able to understand and classify the many types of threats.
  - Remember, we are threat modeling in order to proactively find and resolve security issues across our systems.
- Refresher: What is a threat?
  - How is a threat different from a vulnerability, risk, or problem?
  - A "model" is a representation of a real threat.

![stride](assets/stride.png)

    Source: [https://www.microsoft.com/security/blog/2007/09/11/stride-chart/](https://www.microsoft.com/security/blog/2007/09/11/stride-chart/)

- **What**
- What is STRIDE?
  - Framework composition is an acronym
    - Spoofing Identity
    - Tampering with Data
    - Repudiation
    - Information Disclosure
    - Denial of Service
    - Elevation of Privilege

  > Remember, frameworks give security teams structure to use. STRIDE was never developed as an all-encompassing, "perfect" framework that accounts for all threats using clearly defined boundaries. Many threat types will include multiple elements of STRIDE, or straddle the gray areas. Make frameworks work for you and your team, not the other way around!

Next, let's practice classifying some threats.

- **How**
  - Ref [DEMO.md](DEMO.md)

- **Experimentation and Discovery Ideas**

## Threat Modeling with DFDs

- **Why** (5 min)
  - Why are data flow diagrams (DFDs) used?
    - Represent movement of data as part of threat analysis.
    - Visually represent a threat on a diagram.

- **What** (10 min)
  - What are DFDs?
    - DFD vs Network diagrams
    - Examples

    - ![DFD1](assets/DFD1.png)

    - ![DFD2](assets/DFD2.png)

    - ![DFD3](assets/DFD3.png)

  - What is the Microsoft Threat Modeling Framework?
    - Threat identification and mitigation process
    - ![MS Threat Model](assets/ms-thread-model.png)

  - What are trust boundaries?
    - A trust boundary is everywhere two (or more) principals interact
    - All interesting boundaries are semi-permeable
      – Air gaps
      – Firewalls
      – Require policy mechanisms
    - Formal methods help build boundaries
      – Isolation
      – Type safety
      – Policy languages
      – Reference monitors/kernels
