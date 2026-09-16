# 10 - Managing Software and Updates

## Overall Summary
This lesson covers software management, system updates, and security advisories on Red Hat Enterprise Linux using `dnf` and Red Hat Subscription Management. It details how systems access Red Hat content directly or via an enterprise proxy (Red Hat Satellite). The lesson demonstrates package searching, installation, and selective updates, explaining Red Hat Errata types (RHBA, RHEA, RHSA) and security vulnerability metrics like CVE IDs and CVSS severity scores. Finally, it outlines targeted security patching and reboot verification tools.

## New Jargon
* **DNF (Dandified YUM):** The default software package manager on Red Hat Enterprise Linux used to query, install, update, and remove RPM packages along with their dependencies[cite: 1, 10].
* **Red Hat CDN (Content Delivery Network):** Red Hat's public cloud infrastructure hosting signed software repositories and updates.
* **Red Hat Satellite:** An enterprise management platform that acts as a local proxy, caching content from the Red Hat CDN to serve internal hosts[cite: 4, 10].
* **Errata:** Official Red Hat advisory notices detailing software updates, bug fixes, enhancements, or security patches.
* **RHBA (Red Hat Bug Advisory):** Advisories released to fix non-critical software bugs and stability issues.
* **RHEA (Red Hat Enhancement Advisory):** Advisories introducing new software features, improvements, or hardware enablement.
* **RHSA (Red Hat Security Advisory):** Critical advisories fixing security vulnerabilities, categorized by severity.
* **CVE (Common Vulnerabilities and Exposures):** A standardized, publicly tracked identifier (e.g., `CVE-2024-12345`) assigned to known cybersecurity vulnerabilities[cite: 10].
* **CVSS (Common Vulnerability Scoring System):** A numerical industry scale (0.0 to 10.0) measuring the severity of security vulnerabilities[cite: 10].

## Commands Learnt
* **`subscription-manager identity`:** Displays the active system's registration identity and subscription credentials[cite: 10].
* **`subscription-manager register`:** Registers a RHEL system with Red Hat Subscription Management[cite: 10].
* **`dnf search <keyword>`:** Searches repository metadata for packages matching a keyword (e.g., `dnf search nodejs`)[cite: 10].
* **`dnf install <package>`:** Downloads and installs a software package with its dependencies[cite: 10].
* **`dnf install -y <package>`:** Installs a package while automatically answering "yes" to confirmation prompts[cite: 10].
* **`dnf updateinfo list`:** Lists available errata advisories affecting installed packages[cite: 10].
* **`dnf updateinfo <advisory_id/filename>`:** Displays detailed breakdown text for a specific security advisory or file[cite: 10].
* **`dnf update`:** Updates all installed packages to their latest available repository versions[cite: 10].
* **`dnf update <package>`:** Updates a specific package (e.g., `dnf update nodejs`)[cite: 10].
* **`dnf update --sec-severity=Important --sec-severity=Critical`:** Restricts system updates strictly to advisories categorized as Important or Critical severity[cite: 10].
* **`dnf needs-restarting -r`:** Checks system state to determine whether core service updates require a system reboot[cite: 10].
* **`reboot`:** Restarts the operating system[cite: 10].

## Key Concepts

### 1. Repository Connectivity: Direct CDN vs. Red Hat Satellite
Systems require access to software repositories to install patches and software[cite: 10]:
* **Direct Red Hat CDN Access:** Individual RHEL servers register to Red Hat directly over the public internet (`subscription-manager register`)[cite: 10]. Every server requires outbound internet access to download software directly from Red Hat[cite: 10].
* **Red Hat Satellite Proxy:** The central Satellite server connects to the Red Hat CDN to download and host content once locally[cite: 4, 10]. Internal enterprise servers register directly to Satellite, allowing patch delivery inside isolated or air-gapped networks without granting individual servers internet connectivity[cite: 4, 10].

### 2. Red Hat Errata Types
Updates are packaged into Errata advisories[cite: 10]:
* **RHBA (Bug Advisory):** Fixes software bugs and operational errors[cite: 10].
* **RHEA (Enhancement Advisory):** Adds features, performance optimizations, or hardware updates[cite: 10].
* **RHSA (Security Advisory):** Addresses vulnerabilities to protect system integrity[cite: 10].

### 3. CVE Identifiers & CVSS Severity Scale
* **CVE ID:** Standardized dictionary tracking specific security flaws (e.g., `CVE-2023-38408`)[cite: 10].
* **CVSS Score:** Standardized score from **0.0 to 10.0** assessing risk[cite: 10]:
  * **Low (0.1–3.9):** Minimal operational risk.
  * **Medium (4.0–6.9):** Moderate risk requiring standard patching windows.
  * **High (7.0–8.9):** Serious risk requiring prioritized patching.
  * **Critical (9.0–10.0):** Severe risk enabling remote execution or privilege escalation, requiring immediate mitigation.

### 4. Reading `dnf updateinfo` Output
Running `dnf updateinfo <advisory_id>` provides a detailed summary breakdown[cite: 10]:
```text
===============================================================================
  Important: openssl security and bug fix update
===============================================================================
  Update ID: RHSA-2024:1234
     Type: security
  Updated: 2024-05-10 00:00:00
     Bugs: 221144 - CVE-2024-9999 OpenSSL buffer overflow vulnerability
  Description: An issue was discovered in OpenSSL where memory buffers...
     Severity: Important
```

This output outlines the Advisory ID (RHSA), Severity Level, Associated CVE IDs, Impacted Packages, and a summary of the underlying security vulnerability[cite: 10].

### 5. Targeted Patching & Reboot Checks

* Selective Patching: Use --sec-severity= options to filter patches during emergency security windows without applying non-security updates[cite: 10]:
dnf update --sec-severity=Important --sec-severity=Critical[cite: 10]

* Reboot Verification: Running dnf needs-restarting -r checks if running processes are still referencing old binary libraries in memory[cite: 10]. If kernel or fundamental glibc libraries were updated, the tool alerts the admin to execute reboot[cite: 10].

---

### Main Notes

* Use the -y flag (dnf install -y) cautiously in automated scripts; manually reviewing interactive package changes prevents unintended dependency removals[cite: 10].

* Always run dnf needs-restarting -r after applying kernel or glibc security updates to confirm whether a host reboot is required[cite: 10].

### My Key Learning

Software management on RHEL combines package installation with security advisory analysis[cite: 10]. Understanding CVSS severity ratings and Errata types enables administrators to target critical security patches without disrupting stable production systems[cite: 10].