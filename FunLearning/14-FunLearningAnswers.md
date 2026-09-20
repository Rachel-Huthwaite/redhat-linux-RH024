# 14 - Fun Learning Answers: Using Image Mode with Bootc

Use these answers to check your responses from `14-FunLearningQuestions.md`.

---

### Answers

1. **Defining `bootc`:**
   * `bootc` allows operating systems to be deployed and updated as complete bootable container images (OCI images)[cite: 15]. Unlike traditional systems managed package-by-package with `dnf`, Image Mode updates the entire operating system transactionally as a single unit[cite: 10, 15].

2. **Checking Image Status:**
   * `bootc status`[cite: 15].

3. **OS Upgrades:**
   * `bootc switch quay.io/name/bootc_httpd:2`[cite: 15].

4. **Applying Changes:**
   * Execute a system `reboot`[cite: 15].

5. **Key Advantage:**
   * It eliminates **configuration drift** across servers and provides deterministic, atomic updates with instant rollbacks[cite: 15].