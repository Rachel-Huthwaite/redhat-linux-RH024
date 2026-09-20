# 13 - Fun Learning Answers: Deploying an Application Runtime

Use these answers to check your responses from `13-FunLearningQuestions.md`.

---

### Answers

1. **Service vs. Interactive Session:**
   * `systemd` services automatically start when the host reboots, automatically recover/restart if the application crashes, and integrate directly with system-wide logging without requiring manual terminal restarts[cite: 14].

2. **Unit File Storage:**
   * `/etc/systemd/system/`[cite: 14].

3. **Indexing New Units:**
   * `sudo systemctl daemon-reload`[cite: 14].

4. **Single Command Activation:**
   * `sudo systemctl enable --now myapp`[cite: 12, 14].

5. **Firewall Port Opening:**
   * `sudo firewall-cmd --add-port=8080/tcp`[cite: 14].

6. **Persistence Shortcut:**
   * `!! --permanent`[cite: 12, 14].

7. **Testing Deployment:**
   * `http://localhost:8080`[cite: 14].