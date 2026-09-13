# 05 - Fun Learning Answers: Linux Directories Explained

Use these answers to check your responses from `05-FunLearningQuestions.md`.

---

### Answers

1. **Root Directory:**
   * `/`[cite: 5].

2. **Current Location:**
   * `pwd` (Print Working Directory)[cite: 5].

3. **Shortcut Navigation:**
   * It takes you directly back to your user's home directory (`/home/username` or `/root`)[cite: 5].

4. **Hidden Files:**
   * The `-a` option flag (`ls -a`)[cite: 5].

5. **System Settings:**
   * In `/etc`[cite: 5]. The key best practice is to **always create a backup copy** of the original configuration file before making any changes[cite: 5].

6. **Data Storage Comparison:**
   * `/tmp` holds non-critical temporary data that is periodically cleared by the system or removed on reboot[cite: 5]. 
   * `/var` holds persistent variable data (like system logs and databases) that survives system reboots[cite: 1, 5].

7. **Executables & Libraries:**
   * Executable binaries live in `/usr/bin`, and shared 64-bit library files live in `/usr/lib64`[cite: 5].

8. **Mounting:**
   * `/mnt` is used as a temporary mount point to attach secondary storage devices, network shares, or ISO files into the filesystem hierarchy[cite: 5].

9. **Runtime State:**
   * `/run` stores real-time system runtime state data (like active process IDs and sockets) for the currently running session, so it must start fresh upon boot[cite: 5].

10. **Administrative Home:**
    * `/home` contains subdirectories for regular users on the system (e.g., `/home/john`)[cite: 5].
    * `/root` is the dedicated home directory specifically for the elevated administrative `root` superuser[cite: 5].