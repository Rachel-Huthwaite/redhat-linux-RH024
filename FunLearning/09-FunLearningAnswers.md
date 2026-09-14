# 09 - Fun Learning Answers: File Permissions

Use these answers to check your responses from `09-FunLearningQuestions.md`.

---

### Answers

1. **Permission Values:**
   * Read (`r`) = 4[cite: 9]
   * Write (`w`) = 2[cite: 9]
   * Execute (`x`) = 1[cite: 9]

2. **Directory Execution:**
   * On a file, Execute (`x`) lets you run the file as an executable program or script[cite: 9].
   * On a directory, Execute (`x`) allows traversing (`cd`) into the folder and accessing file metadata[cite: 9].

3. **Octal Decoding:**
   * Owner: $6 \rightarrow$ `rw-`[cite: 9]
   * Group: $4 \rightarrow$ `r--`[cite: 9]
   * Others: $0 \rightarrow$ `---`[cite: 9]
   * **Result:** `rw-r-----`[cite: 9]

4. **Inspecting Directories:**
   * `ls -ld <directory_path>`[cite: 9].

5. **Extreme Modes:**
   * It strips all permissions for User, Group, and Others (`---------`), preventing any access until permissions are restored[cite: 9].

6. **Ownership Changes:**
   * `chown john:devs app.py`[cite: 9].

7. **Evaluation Order:**
   * Linux checks in strict sequence: **Owner (User) $\rightarrow$ Group $\rightarrow$ Others**[cite: 9]. It applies the first set of permissions that matches the accessing account and ignores subsequent sets[cite: 9].

8. **Security Principles:**
   * System entities (users, processes, scripts) should be granted only the minimal permissions required to complete their immediate job, mitigating security risks[cite: 9].

9. **Terminal Multiplexing:**
   * `tmux` keeps terminal sessions running persistently on the server[cite: 9]. If an SSH connection drops, processes continue running and sessions can be re-attached later[cite: 9].