# 13 - Fun Learning Quiz: Deploying an Application Runtime

Test your active recall on the concepts introduced in Lesson 13.

---

### Questions

1. **Service vs. Interactive Session:** Why is running an application as a `systemd` service superior to launching it inside interactive utilities like `tmux` or `screen`?
2. **Unit File Storage:** What target directory path is used when installing custom unit files like `myapp.service` on RHEL?
3. **Indexing New Units:** What specific `systemctl` command must be executed immediately after adding or modifying a unit file in `/etc/systemd/system/`?
4. **Single Command Activation:** What command simultaneously enables `myapp` to launch on boot and executes it in runtime immediately?
5. **Firewall Port opening:** What `firewall-cmd` syntax opens TCP port `8080` for network connectivity?
6. **Persistence Shortcut:** How do you convert the runtime firewall command from Question 5 into a persistent rule using bash history expansion?
7. **Testing Deployment:** What local URL and port can be accessed in a web browser to verify that the deployed runtime application is active locally?