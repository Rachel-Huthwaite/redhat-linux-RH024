# 09 - File Permissions

## Overall Summary
This lesson covers Linux file permissions, explaining how security and access control are enforced across files and directories[cite: 9]. It breaks down the read (`r`), write (`w`), and execute (`x`) permission bits for users (owners), groups, and others, and highlights how execution rights behave differently on files versus directories[cite: 9]. The lesson demonstrates absolute symbolic/numeric permission changes with `chmod` (including recursive updates and extreme numerical modes)[cite: 9], ownership management using `chown`[cite: 9], inspection via `ls -ld`[cite: 9], the principle of least privilege[cite: 9], and workspace management using `tmux`[cite: 9].

## New Jargon
* **File Permissions:** Rules attached to every system file and directory that dictate access rights for users, groups, and others[cite: 9].
* **Read Permission (`r`):** Granting access to read file contents or list directory entries[cite: 9].
* **Write Permission (`w`):** Granting permission to modify/delete file contents or create/delete files inside a directory[cite: 9].
* **Execute Permission (`x`):** Granting permission to execute a binary/script, or to traverse (`cd`) into a directory[cite: 9].
* **Absolute Permission Modes (Octal Notation):** Representing permissions using 3-digit octal numbers where Read=4, Write=2, and Execute=1[cite: 9].
* **`tmux` (Terminal Multiplexer):** A workspace utility that lets users manage multiple terminal sessions inside a single window and keep background processes running persistently[cite: 9].
* **Principle of Least Privilege:** A core security practice stating that users and processes should only be granted the minimum permissions necessary to complete their intended function[cite: 9].

## Commands Learnt
* **`ls -ld`:** Displays detailed permissions and metadata specifically for a directory itself rather than listing its contents[cite: 9].
* **`chmod` (Change Mode):** Modifies file and directory permissions[cite: 9].
  * `chmod 640 foo`: Sets User to `rw-` (6), Group to `r--` (4), and Others to `---` (0) on file `foo`[cite: 9].
  * `chmod -R 755 /bar`: Recursively (`-R`) sets permissions to `rwxr-xr-x` across `/bar` and all nested contents[cite: 9].
  * `chmod 000 file`: Revokes all permissions for User, Group, and Others (`---------`)[cite: 9].
  * `chmod 001 file`: Grants execution permission strictly to Others (`-------x`)[cite: 9].
  * `chmod 005 file`: Grants read and execute permissions strictly to Others (`------r-x`)[cite: 9].
* **`chown` (Change Owner):** Modifies user and/or group ownership of files and directories[cite: 9].
  * `chown username file`: Changes owning user[cite: 9].
  * `chown :groupname file` or `chgrp groupname file`: Changes owning group[cite: 9].
  * `chown username:groupname file`: Simultaneously changes both owning user and owning group[cite: 9].
* **`tmux`:** Launches a terminal session multiplexer to manage persistent terminal screens[cite: 9].

## Key Concepts

### 1. Permissions on Files vs. Directories
Permissions function differently based on whether they are applied to standard files or directories[cite: 9]:

| Permission | Applied to a File | Applied to a Directory |
| :--- | :--- | :--- |
| **Read (`r`)** | Read file contents[cite: 9]. | List file names inside the directory using `ls`[cite: 9]. |
| **Write (`w`)** | Modify or overwrite file contents[cite: 9]. | Create, rename, or delete files inside the directory[cite: 9]. |
| **Execute (`x`)** | Execute file as a script or binary program[cite: 9]. | Traverse into the directory (`cd`) and access file metadata[cite: 9]. |

> **Crucial Distinction:** Having `w` (write) permission on a file lets you edit file text[cite: 9]. However, deleting or renaming a file requires `w` (write) and `x` (execute) permissions on the **parent directory** containing that file[cite: 9].

### 2. Numerical (Octal) Permissions Breakdown
Octal representation combines values for three categories: **User (Owner)**, **Group**, and **Others**[cite: 9]:
* `r` = 4
* `w` = 2
* `x` = 1

**Examples of Octal Modes:**
* `640` $\rightarrow$ User: $4+2=6$ (`rw-`), Group: $4$ (`r--`), Others: $0$ (`---`)[cite: 9].
* `755` $\rightarrow$ User: $4+2+1=7$ (`rwx`), Group: $4+1=5$ (`r-x`), Others: $4+1=5$ (`r-x`)[cite: 9].
* `000` $\rightarrow$ No permissions granted to anyone (`---------`)[cite: 9]. Even the owner cannot read or edit without re-granting permissions[cite: 9].
* `001` $\rightarrow$ Only Others can execute (`-------x`)[cite: 9].
* `005` $\rightarrow$ Only Others can read and execute (`------r-x`)[cite: 9].

### 3. Evaluation Order of Permissions
Linux evaluates permission rights in a strict top-down order based on the user requesting access[cite: 9]:
1. **User (Owner):** If the active account matches the file owner, the owner permissions apply exclusively[cite: 9].
2. **Group:** If the account is not the owner but belongs to the owning group, group permissions apply exclusively[cite: 9].
3. **Others:** If neither user nor group matches, the "others" permission set applies[cite: 9].

### 4. What is `tmux`?
`tmux` (Terminal Multiplexer) is a tool that runs persistent terminal sessions detached from terminal windows[cite: 9]. If an SSH connection drops, processes running inside a `tmux` session continue executing on the server uninterrupted[cite: 9].

## Main Notes
* Always inspect directory permissions using `ls -ld <directory>`[cite: 9]. Running `ls -l <directory>` shows the contents inside, not the parent directory permissions[cite: 9].
* Always adhere to the **Principle of Least Privilege**: Grant only the minimal access necessary for users and applications to complete their tasks[cite: 9].

## My Key Learning
Directory permissions govern structural actions like file creation or deletion, while file permissions govern file contents[cite: 9]. Linux evaluates permissions in a strict sequence (Owner $\rightarrow$ Group $\rightarrow$ Others), applying the first match encountered[cite: 9].