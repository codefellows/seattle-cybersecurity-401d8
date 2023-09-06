# Lecture Notes: Pass the Hash with Mimikatz

## Topic 1

- **Why** (5 min)
  - Why are we studying Mimikatz?
    - This is a popular tool used to perform key post-exploitation activities such as lateral movement within a network.
  - A major pain point for Windows systems exists with the WDigest feature
    - Win10 disables WDigest but still ships with it (just like SMB) so an attacker can simply turn on WDigest if they achieve local admin.

- **What** (10 min)
  - Linux Passwords
    - The `/etc/passwd` directory contains information necessary for the user login
    - The `passwd` file contains the following information:
      - Username
      - Password ('x') since the actual hash is stored in the `/etc/shadow` file
      - User ID (UID)
      - Group ID (GID)
      - Information about User ID
      - Home directory (/home/username)
      - Default shell (/bin/bash)

  - What is an "administrator" in Windows terms?
    - Typically, user accounts can be assigned into the administrators group to receive those privileges. Remember RBAC?
    - Secretly, Windows maintains a hidden Administrator account that is the final authority and has even higher privileges than a administrator-classed user.

  - What is NTLM?
    - "Windows Challenge/Response (NTLM) is the authentication protocol used on networks that include systems running the Windows operating system and on stand-alone systems."
    - "NTLM credentials are based on data obtained during the interactive logon process and consist of a domain name, a user name, and a one-way hash of the user's password. NTLM uses an encrypted challenge/response protocol to authenticate a user without sending the user's password over the wire. Instead, the system requesting authentication must perform a calculation that proves it has access to the secured NTLM credentials."

  - What is SAM (Security Account Manager)?
    - A database file in Windows that stores users passwords as **NTLM Hashes**
    - SAM registry entry is located in the registry hive `HKEY_LOCAL_MACHINE`
    - SAM file is located in `C:\Windows\System32\config`
    - SAM file is targeted by hash dumping tools

  - What is Kerberos?
    - A computer network security protocol that authenticates service requests between two or more trusted hosts across an untrusted network
    - Uses secret-key cryptography and a trusted third-party for authenticating client-server applications and verifying users' identities
    - Components:
      - Client
      - Server
      - Authentication Server (AS)
      - Key Distribution Center (KDC)
      - Ticket Granting Server (TGS)

  - Lateral Movement
    - A post-exploitation tactic used to maneuver deeper into a network in search of sensitive data or high-value assets.

  - What is Mimikatz?
    - A post-exploitation tool used to perform lateral movement on Windows systems.
    - A **pass the hash** attack is a lateral movement technique where the password hash from one computer is used to authenticate into another.
    - Mimikatz exploits a vulnerability in the WDigest feature.
