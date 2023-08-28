# Lecture Notes: XSS with w3af, DVWA

## Review Ops Challenge Class 35

## Topic 1: XSS with w3af, DVWA

- **Why** (5 min)
  - Why should we study vulnerabilities as it relates to our entering the security field?

    > Storytime! "In 1994, Lou Montulli developed cookies for the first time. As a Netscape Communications employee, Montulli worked alongside John Giannandrea to develop cookies into a unique solution that would help make shopping carts for e-commerce stores possible. This means the first primary usage of cookies on the internet was to establish whether a visitor coming to Netscape’s website had already visited it or not. At the start, all supported browsers accepted cookies by default, which meant hardly any end users were aware of their use or presence. However, in February 1996, this changed, when their use, purpose, and existence were revealed in a piece published by The Financial Times. Over the next few years, the media placed cookies under intense scrutiny due to the privacy risks created as they tracked visitors across a website." -[HTML.com](https://html.com/resources/cookies-ultimate-guide/#ixzz6ealjiGv1)

    - The fun answer is this: If I steal your cookie, I can buy whatever I want from Amazon and use YOUR identity, including your credit card and so forth. This makes cookie theft not only tasty, but immensely profitable as a cyber crime.
    - DO: Draw out a cookie theft scenario.
    - Here's the more textbook answer below.
    - Large companies that face constant cyber attacks use vulnerability assessments to proactively identify weaknesses in their defenses
    - May employ vulnerability analysts or contract third party assessments
    - Here are some issues that vulnerability assessments help organizations deal with:
      - Unnecessary open shares
      - Unused user accounts
      - Unnecessary open ports
      - Rogue devices connected to your systems
      - Dangerous script configurations
      - Servers allowing use of dangerous protocols
      - Incorrect permissions on important system files
      - Running of unnecessary, potentially dangerous services.
    - Apart from these misconfigurations, when running a vulnerability assessment on your network you might find several security issues with a wide range of software and hardware including:
      - Default passwords on certain devices
      - Unnecessary services running on some devices
      - Running web services that contain known vulnerabilities
      - Dangerous applications such as peer-to-peer applications
      - Third-party applications that are a vulnerability to known exploits.

- **What** (10 min)
  - What is a vulnerability?
      - NIST definition: Weakness in an information system, system security procedures, internal controls, or implementation that could be exploited or triggered by a threat source.
      - Important to differentiate vulnerability, exploit, and risk.
      - Not all vulnerabilities are likely to be exploited or high risk.
      - Prioritize your vulnerabilities.

  > Careful with the next section on careers; the language and scope for job titles varies dramatically! Emphasize the job may or may not include network vulnerabilities VS application security vulnerabilities analysis.

  - What is a [vulnerability analyst](https://www.comptia.org/blog/your-next-move-vulnerability-analyst)?
    - A security professional that detects weaknesses in networks and then takes measures to help the organization correct and strengthen the system's security levels.
    - Job duties:
      - Develops risk-based mitigation strategies for networks, operating systems, and applications
      - Compiles and tracks vulnerabilities and mitigation results to quantify program effectiveness
      - Creates and maintains vulnerability management policies, procedures, and training
      - Review and define requirements for information security solutions
      - Organize network-based scans to identify possible network security attacks and host-based scans to identify vulnerabilities in workstations, servers, and other network hosts.
    - Salary range: $75,000-92,600
    - Demand: From 2016 to 2026, CompTIA projects an increase of 19 percent with 17,917 net new jobs expected during that 10-year period.
    - Related job titles:
      - Penetration Tester
      - Vulnerability Tester
      - Security Analyst (II)
      - Vulnerability Assessment Analyst
      - Network Security Operations
      - Application Security Vulnerability

  - What is the [MITRE CVE database](https://cve.mitre.org/cve/)?
    - CVE® is a dictionary of publicly disclosed cybersecurity vulnerabilities and exposures that is free to search, use, and incorporate into products and services, per the terms of use.
    - DO: Review an example CVE together.
    - What is the significance of submitting a CVE? A: Major milestone achievement in an offensive security professional's career.

  - What is [w3af](https://w3af.org/)?
    - w3af stands for "Web Application Attack and Audit Framework."
    - Link to [official documentation](http://docs.w3af.org/en/latest/basic-ui.html)
    - Framework for securing web apps by finding and exploiting their vulnerabilities
    - Coded in Python and is open source

  - What are some HTML basics you'll need to know for today?
    - Fun throwback; any MySpace web designers in the room?
    - Class can brush up on their MySpace skills (joking, I mean HTML) at [w3schools](https://www.w3schools.com/html/html_basic.asp)
    - Demonstrate

      ```html
      <!DOCTYPE html> tag
      <html>
      <body>
      <p> tag </p>
      <h1> tag <h1>
      </body>
      </html>
      ```

  - What is cross-site scripting (XSS)?
    - Malicious code injection performed on client side of a web app, typically using Javascript and HTML.
    - Some XSS attacks save a malicious script on the web server which can be executed in the victim's browser
    - The main purpose of this attack is to steal the other user’s identity data – cookies, session tokens and other information.
      - In most of the cases, this attack is being used to steal the other person‘s cookies.
      - Cookies help us to log in automatically.
      - Therefore with stolen cookies, we can login with the other identities. And this is one of the reasons, why this attack is considered as one of the riskiest attacks.

- **How** (30 min)

  - Refer to [DEMO.md](DEMO.md)

- **Experimentation and Discovery Ideas**

Consider revising XSS lab to be more advanced; have student complete a full XSS cookie redirect attack as depicted by [Computerphile](https://www.youtube.com/watch?v=T1QEs3mdJoc&ab_channel=Computerphile)
