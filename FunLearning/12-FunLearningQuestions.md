# 12 - Fun Learning Quiz: Managing System Startup Services with systemd

Test your active recall on the concepts introduced in Lesson 12.

---

### Questions

1. **System Initializer:** What system service manager originally contributed by Red Hat is used by major Linux distributions to manage boot startup and daemons?
2. **`systemd` Unit Types:** Match the `systemd` unit type (`service`, `socket`, `timer`, `path`, `target`) to its function:
   * A. Triggers actions based on file modifications.
   * B. Groups units together to establish system states.
   * C. Manages background daemons and applications.
   * D. Listens on network ports for on-demand activation.
   * E. Handles scheduled tasks and time-based triggers.
3. **Combined Service Control:** What single `systemctl` command enables a service to start at boot and immediately launches it in runtime?
4. **Inspecting Service Status:** What command allows you to view the active running state, process ID (PID), and recent log lines for `httpd`?
5. **Firewall Persistence:** What flag must be appended to `firewall-cmd` commands to ensure open service ports persist across reboots?
6. **History Repeat Shortcut:** What bash shortcut re-runs your exact prior terminal command?
7. **String Substitution Shortcut:** If you ran `systemctl restart httpd`, what exact substitution shortcut transforms and executes that command as `systemctl stop httpd`?