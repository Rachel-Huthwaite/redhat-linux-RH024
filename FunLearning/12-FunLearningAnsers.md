# 12 - Fun Learning Answers: Managing System Startup Services with systemd

Use these answers to check your responses from `12-FunLearningQuestions.md`.

---

### Answers

1. **System Initializer:**
   * `systemd`[cite: 12].

2. **`systemd` Unit Types:**
   * **A. Triggers actions based on file modifications:** Path unit (`.path`)[cite: 12]
   * **B. Groups units together to establish system states:** Target unit (`.target`)[cite: 12]
   * **C. Manages background daemons and applications:** Service unit (`.service`)[cite: 12]
   * **D. Listens on network ports for on-demand activation:** Socket unit (`.socket`)[cite: 12]
   * **E. Handles scheduled tasks and time-based triggers:** Timer unit (`.timer`)[cite: 12]

3. **Combined Service Control:**
   * `systemctl enable --now httpd`[cite: 12].

4. **Inspecting Service Status:**
   * `systemctl status httpd`[cite: 12].

5. **Firewall Persistence:**
   * `--permanent` (e.g., `firewall-cmd --add-service=http --permanent`)[cite: 12].

6. **History Repeat Shortcut:**
   * `!!`[cite: 12].

7. **String Substitution Shortcut:**
   * `^restart^stop`[cite: 12].