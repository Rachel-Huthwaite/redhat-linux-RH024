# 08 - Organizing Local Users and Groups

## Overall Summary
This lesson covers user and group management on Red Hat Enterprise Linux[cite: 8]. It explains the system configuration files storing account and credential data (`/etc/passwd` and `/etc/shadow`), step-by-step user creation and modification (`useradd`, `usermod`, `passwd`, `userdel`), and administrative privileges via `sudo` and the `wheel` group[cite: 8]. It also examines security practices like account locking versus deletion, orphan file risk with dynamic UIDs, group administration, and central authentication using Red Hat Identity Management (IdM)[cite: 8].

## New Jargon
* **Local User:** An account defined directly on a standalone system within `/etc/passwd` rather than managed centrally via a directory service[cite: 8].
* **UID (User Identifier):** A unique numerical ID assigned by Linux to track and enforce file permissions for every user account[cite: 8].
* **GID (Group Identifier):** A unique numerical ID assigned to a group to manage collective resource permissions[cite: 8].
* **`wheel` Group:** A special administrative group in RHEL; members are granted permission to run administrative commands using `sudo`[cite: 8].
* **Orphan Files:** Files whose owner UID no longer maps to an active account in `/etc/passwd` (often caused by deleting a user without removing their files)[cite: 8].
* **Red Hat IdM (Identity Management):** Red Hat's enterprise solution for central identity, authentication, and access control across Linux environments[cite: 8].

## Commands Learnt
* **`cat /etc/passwd`:** Displays all local user account configurations on the system[cite: 8].
* **`sudo` (SuperUser Do):** Executes a command with elevated superuser (`root`) privileges[cite: 8].
* **`sudo -i`:** Opens an interactive root shell with root environment variables loaded[cite: 8].
* **`useradd`:** Creates a new local user account[cite: 8].
  * `useradd alisson`: Creates user account `alisson`[cite: 8].
* **`passwd`:** Manages user passwords and account locking status[cite: 8].
  * `passwd alisson`: Sets or changes the password for user `alisson`[cite: 8].
  * `passwd -l alisson`: Locks the user account by prefixing the password hash in `/etc/shadow`[cite: 8].
  * `passwd -u alisson`: Unlocks a locked user account[cite: 8].
* **`usermod`:** Modifies user account parameters[cite: 8].
  * `usermod -s /bin/zsh alisson`: Changes user `alisson`'s login shell to `/bin/zsh`[cite: 8].
  * `usermod -aG groupname username`: Appends (`-a`) a secondary group (`-G`) to a user without removing existing group memberships[cite: 8].
* **`userdel`:** Removes a local user account[cite: 8].
  * `userdel -r alisson`: Deletes user `alisson` and recursively removes their home directory and mail spool[cite: 8].
* **`groupadd`:** Creates a new system group[cite: 8].
  * `groupadd devs`: Creates group `devs`[cite: 8].
* **`groupmod`:** Modifies group parameters[cite: 8].
  * `groupmod -n developers devs`: Renames group `devs` to `developers`[cite: 8].
* **`groupdel`:** Removes a system group[cite: 8].
* **`id`:** Displays current user identity, UID, primary GID, and secondary group memberships[cite: 8].
* **`groups`:** Prints the names of all groups a specified user belongs to[cite: 8].
* **`find / -uid <UID> 2>/dev/null`:** Searches the filesystem for files owned by a specific UID while redirecting error messages (`Permission denied`) to `/dev/null`[cite: 8].
* **`su -`:** Switches current shell session to the `root` superuser account with a full login shell environment[cite: 8].

## Key Concepts

### 1. Essential User & Security Files
* **`/etc/passwd`:** Publicly readable file containing basic user account info (username, UID, primary GID, home directory, login shell)[cite: 8].
* **`/etc/shadow`:** Restricted file accessible only by root storing encrypted user password hashes, expiration dates, and security parameters[cite: 8].

### 2. Deep Dive: Account Deletion, UIDs, and Orphan Files
When a user is created, Linux assigns them a numerical UID (e.g., `1001`)[cite: 8]. File ownership is tracked by this numerical UID, not by the username string[cite: 8].

* **Risk of Standard `userdel`:** Running `userdel alisson` removes the username from `/etc/passwd`, but leaves their files on disk owned by UID `1001`[cite: 8]. If a new user is created later, Linux reuses UID `1001`[cite: 8]. The new user automatically inherits access to all orphaned files left by the deleted user[cite: 8].
* **Remediation Options:**
  1. Use `userdel -r alisson` to remove the user's home directory and files simultaneously[cite: 8].
  2. Locate remaining orphan files using `find / -uid 1001 2>/dev/null` before creating new accounts[cite: 8].
  3. **Locking Account (`passwd -l`):** Preferred in enterprise operations over immediate deletion[cite: 8]. Locking disables login access while preserving the account UID mapping and audit history[cite: 8].

### 3. `sudo -i` vs. `su -`
* **`sudo -i`:** Grants root privileges based on individual user authentication (entering the user's own password)[cite: 8]. Provides strict command auditing in `/var/log/secure`[cite: 1, 8].
* **`su -`:** Requires knowing the shared `root` account password directly[cite: 8]. Highly discouraged in enterprise environments because it obscures identity auditing and forces sharing superuser passwords[cite: 8].

### 4. Local vs. Centralized Identity Management (Red Hat IdM)
Local user files (`/etc/passwd`) become unmanageable across large server deployments[cite: 8]. Enterprise environments use **Red Hat Identity Management (IdM)** (or Active Directory) to centralize user credentials, group policies, SSH keys, and sudo permissions across thousands of systems without maintaining local accounts individually[cite: 8].

## Main Notes
* Always use `-aG` when adding groups via `usermod`[cite: 8]. Leaving off the `-a` (append) flag will overwrite all of a user's existing secondary groups[cite: 8].
* The `2>/dev/null` syntax redirects standard error output (File Descriptor 2) to the null device, suppressing permissions warnings during system-wide `find` operations[cite: 8].

## My Key Learning
File ownership in Linux is bound to numerical UIDs rather than usernames[cite: 8]. Locking accounts (`passwd -l`) or removing home directories during deletion (`userdel -r`) is critical to prevent security breaches caused by UID recycling and orphan file exposure[cite: 8].