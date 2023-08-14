# Lecture Notes: Remote Code Execution

## Threat Modeling and Analysis

**Why**

- Why should we study threat modeling and analysis?
  - **Cyber threat analysts** are information security professionals who leverage skills and expertise of network engineering to mitigate and avoid cyberattacks on the organization or its employees. Threat analysts identify vulnerabilities, study digital forensics, and conduct threat modeling in order to monitor and defend against threats faced by organizational infrastructure.

**What**

- What is threat analysis?
  - Cyber **threat analysis** is a process used by cybersecurity threat analysts to study and align a particular organization's defenses against its potential or realized cyber threats
  - According to software engineer Goran Aviani, the goal of a threat analysis is to answer the four questions of:
    - What are we working on?
    - What are the things that can go wrong?
    - How do we go about problems that occur?
    - Did we do a good job?

- What is threat modeling?
  - Cyber **threat modeling** is the structured process used to determine potential security threats and weaknesses, assess risk levels per threat and implement mitigations against specific threats.

## Lecture: Remote Code Execution

**Why**

- Why should we prepare to defend against remote code execution?
  - Discuss [MS15-011: Vulnerability in Group Policy could allow remote code execution: February 10, 2015](https://support.microsoft.com/en-us/topic/ms15-011-vulnerability-in-group-policy-could-allow-remote-code-execution-february-10-2015-91b4bda2-945d-455b-ebbb-01d1ec191328)

- Why is PowerShell important in cybersecurity?
  - "PowerShell represents one of the most interesting and powerful languages for a pentesting purpose."
  - "...for us, as pentesters, PowerShell represent a powerful shell and scripting language which is present (in most cases from windows 7, it’s integrated by default) on our pentest targets and provide to us specially a powerful post-exploitation “tool/language” that can give us so much power and a very big attack surface/possibility." -[InfosecInstitute](https://resources.infosecinstitute.com/topic/powershell-for-pentesters-part-1-introduction-to-powershell-and-cmdlets/)

**What**

- What is remote code execution?
  - **Remote code execution (RCE)** is a class of security vulnerabilities that allows a malicious actor to execute any code of their choice on a remote machine over LAN, WAN, or the Internet

- What is a post-exploitation framework?
  - **Post-exploitation** includes the phases of operation once a victim's system has been compromised by the attacker.
  - Examples of post-exploitation frameworks include Empire and Metasploit.

- What is PowerShell Empire?
  - **PowerShell Empire** is a pure PowerShell post-exploitation agent built on cryptologically-secure communications and a flexible architecture.
  - Empire implements the ability to run PowerShell agents without needing powershell.exe
  - Includes rapidly deployable post-exploitation modules ranging from key loggers to Mimikatz
  - Supports adaptable communications to evade network detection
  - Presented in an accessible framework (unified)

- What is Invoke-PsExec?
  - **Invoke-PsExec** is a cmdlet that lets you execute PowerShell and batch/cmd.exe code asynchronously on target Windows computers, using PsExec.exe.
  - PsExec can be downloaded from the SysInternals suite on Microsoft's site
  - Remember, a batch file ends in .bat and contains non-PowerShell Windows commands only in the form of a script.

**How**

- How can we defend against RCE threats?

Ref. [DEMO.md](DEMO.md)
