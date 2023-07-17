# Demos: Data File Encryption and Hashing

## Data File Encryption and Hashing

Reference [How are passwords stored in Linux (Understanding hashing with shadow utils)](https://www.slashroot.in/how-are-passwords-stored-linux-understanding-hashing-shadow-utils) for this demonstration.

- Demonstrate where Linux stores its passwords.
  - `/etc/passwd`
  - `/etc/shadow`

Let's understand each and every field of the output of /etc/passwd, that are separated by a ":".
1. Username - what you type when you log into the system.
2. Password - this field is set to 'x', and the password is stored in /etc/shadow
3. UID - User identifier assigned to each user. Used by the OS to refer to a user
4. GID - User's group identifier number
5. GECOS - or full name of the user. This field contains a list of comma-separated values with the following information: User's full name, Room number, work phone number, home phone number, other contact information.
6. Home directory - Absolute path to the user's home directory. Contains the user's file and configurations.
7. Login Shell - the absolute path to the user's login shell. The shell that is started when the user logs into the system.

Let's understand each and every field of the output of /etc/passwd, that are separated by a ":".
1. Username - what you type when you log into the system
2. Password - encrypted password in hash format
3. Last password change - The date of the last password change
4. Minimum - minimum number of days required between password changes
5. Maximum - maximum number of days the password is valid, after that user is forced to change passwords again
6. Warn - number of days before password is to expire that user is warned that the password must be changed
7. Inactive - number of days after password expires that account is disabled
8. Expire - The date of expiration of the account, expressed as the number of days since Jan 1, 1970

Demonstrate the process of putting a public key in the `.ssh/authorized_keys` file and test the SSH connection.

After this, demonstrate SCP command syntax. Students will need to perform SCP from their local box to their EC2 box for this lab.

Example syntax:
`scp your_username@remotehost.edu:foobar.txt /some/local/directory`

Source: [hypexr.org](http://www.hypexr.org/linux_scp_help.php)
