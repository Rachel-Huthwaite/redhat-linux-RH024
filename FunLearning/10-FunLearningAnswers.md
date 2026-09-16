# 10 - Fun Learning Answers: Managing Software and Updates

Use these answers to check your responses from `10-FunLearningQuestions.md`.

---

### Answers

1. **Checking Registration:**
   * `subscription-manager identity`[cite: 10].

2. **Network Architecture:**
   * **Direct CDN:** Every server requires outbound internet access to download content directly from Red Hat[cite: 10].
   * **Satellite Proxy:** Only the Satellite server needs internet access to download and cache repository content once; internal client systems download updates locally from Satellite without direct internet exposure[cite: 4, 10].

3. **Automated Installation:**
   * The `-y` flag (e.g., `dnf install -y nodejs`)[cite: 10].

4. **Errata Types:**
   * **RHBA (Red Hat Bug Advisory):** Non-critical software bug fixes[cite: 10].
   * **RHEA (Red Hat Enhancement Advisory):** Feature enhancements and new capabilities[cite: 10].
   * **RHSA (Red Hat Security Advisory):** Security vulnerability patches[cite: 10].

5. **Vulnerability Tracking:**
   * **CVE:** Common Vulnerabilities and Exposures[cite: 10].
   * **CVSS:** Common Vulnerability Scoring System (0.0 to 10.0 scale)[cite: 10].

6. **Inspecting Advisories:**
   * `dnf updateinfo list`[cite: 10].

7. **Selective Security Updates:**
   * `dnf update --sec-severity=Important --sec-severity=Critical`[cite: 10].

8. **Reboot Verification:**
   * `dnf needs-restarting -r`[cite: 10].