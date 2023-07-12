# Lecture Notes: Cyber Risk Analysis

## Lecture Outline

- **Why** (5 min)
- Why do we need to learn how to communicate risk?
  - Our core mission is to mitigate cyber risk.

- **What** (10 min)
- What are due care and due diligence?
  - Showing due care and due diligence is the only way to disprove negligence in an occurrence of loss.
  - **Due care** is using reasonable care to protect the interests of an organization.
    - Example: Developing a formalized security structure including policies and procedures.
  - **Due diligence** is practicing the activities that maintain the due care effort.
    - Example: continued application of this security structure onto the IT infrastructure
- What is risk?
  - CompTIA indicates there is a relationship between vulnerability, threat, and risk.
    - A **vulnerability** is a weakness that could be triggered accidentally or exploited intentionally to cause a security breach.
    - A **threat** is the potential for someone or something to exploit a vulnerability and breach security. A threat may be intentional or unintentional.
    - **Risk** is the likelihood and impact (or consequence) of a threat actor exploiting a vulnerability.
- What is the risk management lifecycle (ISC2)?
  - Risk Assessment
    - Categorize, Classify and Valuate Assets
    - Know/Identify Threats and Vulnerabilities
  - Risk Analysis
    - Qualitative
    - Quantitative
  - Risk Mitigation/Response
    - Reduce/Avoid
    - Transfer
    - Accept/Reject

- Risks are first evaluated and identified
  - Audits
  - Vulnerability scanners

- Risk can be evaluated:
  - Quantitatively
    - CompTIA Sec+ Example 1: Vulnerability + Threat = Risk
    - CompTIA Sec+ Example 2: Risk = Impact * Likelihood
    - This involves assigning monetary values to risk components.
    - CISSP Example:
      - **Asset Value (AV)** – How much is the asset worth?
      - **Exposure factor (EF)** – Percentage of Asset Value lost?
      - **Single Loss Expectancy (SLE)**:
        - What does it cost if it happens once?
        - SLE = AV x EF
      - **Annual Rate of Occurrence (ARO)** is how often this will happen per year.
      - **Annualized Loss Expectancy (ALE)** is what it cost per year if we do nothing.
        - ALE = SLE x ARO
      - **Total Cost of Ownership (TCO)** is the mitigation cost: upfront + ongoing cost (Normally Operational)
    - Example quantitative risk exercise
      - Laptop – Theft/Loss (unencrypted).
        - The Laptop ($1,000) + PII ($9,000) per loss (AV).
        - It is a 100% loss, it is gone (EF)
        - Loss per laptop is $10,000 (AV) x 100% (EF) = (SLE)
        - The organization loses 25 Laptops Per Year (ARO)
        - The annualized loss is $250,000 (ALE)
  - Qualitatively
    - Softer approach, does not use data quantification
    - Rating system is used instead
    - Requires judgment, best practices, intuition, and experience
    - Methods
      - Brainstorming
      - Delphi technique
        - Assumes structured group decisions are more accurate than unstructured group decisions
        - Questionnaires answered in rounds, then an anonymous summary is provided from the previous round to the group
      - Storyboarding
      - Focus groups
      - Surveys
      - Questionnaires
      - Checklists
      - One on one meetings
      - Interviews
- Risk Mitigation/Response
  - **Risk avoidance**
    - Determining that the impact and/or likelihood of a specific risk is too great to be offset by the potential benefits and not performing a certain business function because of that determination.
  - **Risk mitigation**
    - Putting security controls in place to attenuate the possible impact and/or likelihood of a specific risk.
  - **Risk transference**
    - Paying an external party to accept the financial impact of a given risk.
    - Example: Cyber insurance

- If you need a good resource on risk definitions, use the [CISSP student glossary](https://www.isc2.org/Certifications/CISSP/CISSP-Student-Glossary). This is also a fantastic resource for other security terminology you may encounter throughout this course.

- Can risk be eliminated?
  - Cyber risk can't be fully eliminated, but it can be significantly mitigated.
  - **Residual risk** consists of the risk remaining after security controls have been put in place as a means of risk mitigation.

- What is the NIST RMF?
  - The **NIST Risk Management Framework (RMF)** is voluntary guidance, based on existing standards, guidelines, and practices for organizations to better manage and reduce cybersecurity risk. In addition to helping organizations manage and reduce risks, it was designed to foster risk and cybersecurity management communications amongst both internal and external organizational stakeholders.

- What is cyber hygiene?
  - **Cyber hygiene** includes practices and precautions that facilitate keeping sensitive data organized, safe, and secure from exfiltration and attack.

- **How** (30 min)
- How do security teams work to mitigate risk for their employer or clientele?
  - Regularly evaluate for cyber hygiene, perform vulnerability scans and assessment, and thereby generate risk assessments which facilitate better organizational decision making
