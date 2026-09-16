# 11 - Fun Learning Answers: Managing Networking

Use these answers to check your responses from `11-FunLearningQuestions.md`.

---

### Answers

1. **Interfaces vs. Profiles:**
   * Only **one** profile can be active on an interface at any single point in time[cite: 11].

2. **Shortened Profile Listing:**
   * `nmcli c s` (or `nmcli con show`)[cite: 11].

3. **Checking Network Routes:**
   * `ip r s` (or `ip route show`)[cite: 11].

4. **Verifying DNS:**
   * `/etc/resolv.conf`[cite: 11].

5. **Static IP Configuration:**
   * `ipv4.method manual`[cite: 11].

6. **Deleting Profiles:**
   * `nmcli con del datacenter`[cite: 11].

7. **Interactive Management:**
   * `nmtui`[cite: 11].