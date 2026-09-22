# 17 - Fun Learning Answers: Managing Systems with RHEL Web Console

Use these answers to check your responses from `17-FunLearningAnswers.md`.

---

### Answers

1. **Underlying Architecture:**
   * It uses direct native Linux system commands and standard APIs under the hood—no secret backdoors or custom middleman APIs[cite: 18].

2. **Web Console Access:**
   * Port `9090` (e.g., `https://rhel10:9090`)[cite: 18].

3. **Socket Activation:**
   * `sudo systemctl enable --now cockpit.socket`[cite: 18].

4. **Privilege Escalation:**
   * By clicking the **"Turn on Administrative Access"** button in the top navigation bar (the equivalent of `sudo -i`)[cite: 18].

5. **Dashboard Blocks:**
   * Health[cite: 18]
   * Usage[cite: 18]
   * System Information[cite: 18]
   * Configuration[cite: 18]

6. **Log Inspection:**
   * **Boot** selector (boot session filter)[cite: 18]
   * **Priority** dropdown (severity filter)[cite: 18]

7. **Installing Extensions:**
   * `sudo dnf install -y cockpit-*`[cite: 18].