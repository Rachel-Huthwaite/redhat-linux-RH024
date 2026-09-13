# 08 - Fun Learning Answers: Organizing Local Users and Groups

Use these answers to check your responses from `08-FunLearningQuestions.md`.

---

### Answers

1. **User Databases:**
   * `/etc/passwd` stores user account metadata[cite: 8]. 
   * `/etc/shadow` securely stores encrypted password hashes and security policies[cite: 8].

2. **Account Creation:**
   * Create account: `useradd alisson`[cite: 8]
   * Set password: `passwd alisson`[cite: 8]

3. **Modifying Shells:**
   * `usermod -s /bin/zsh alisson`[cite: 8].

4. **Group Assignment:**
   * `usermod -aG <groupname> <username>` (the `-a` ensures the append operation)[cite: 8].

5. **Account Locking:**
   * Command: `passwd -l alisson`[cite: 8].
   * Reason: Locking revokes access immediately while retaining user ownership mappings, logs, and files for audit purposes[cite: 8].

6. **Orphan File Risk:**
   * Standard `userdel` leaves orphaned files owned by UID `1001` on disk[cite: 8]. When a new user is created and assigned UID `1001`, they inherit ownership and read/write rights over the former user's leftover data[cite: 8].

7. **Finding Files by UID:**
   * `find / -uid 1001 2>/dev/null`[cite: 8].

8. **Administrative Access:**
   * The `wheel` group[cite: 8].

9. **Authentication Methods:**
   * `sudo -i` prompts for the individual user's password and logs all actions to individual accounts[cite: 8].
   * `su -` requires sharing the master `root` password directly and obscures individual accountability in logs[cite: 8].

10. **Scalability:**
    * Managing local `/etc/passwd` files across hundreds of servers is unscalable and prone to policy drift[cite: 8]. Central solutions like Red Hat IdM manage credentials, access rules, and SSH keys from a single central console[cite: 8].