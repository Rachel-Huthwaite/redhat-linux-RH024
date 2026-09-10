# 01 - Linux Distributions

## Overall Summary
This lesson explores the foundation of Linux distributions and details the Red Hat ecosystem pipeline. All Linux distributions share the same central Linux Kernel; what differentiates them are their default tools, system configurations, software package managers, and release schedules[cite: 1]. 

Red Hat relies on and contributes heavily to an upstream open-source model[cite: 1]—flowing from community open-source projects into Fedora Linux, then into CentOS Stream, and finally into Red Hat Enterprise Linux (RHEL)[cite: 1]. RHEL delivers predictability, enterprise-grade stability, and a structured 10-year lifecycle support model[cite: 1].

## New Jargon
* **Linux Kernel:** The core software layer that manages hardware interactions and system resources, shared across all Linux distros[cite: 1].
* **Linux Distribution (Distro):** A complete operating system built around the Linux Kernel, bundled with specific applications, package managers, and configurations[cite: 1].
* **Upstream / Downstream:** Upstream refers to source project development where new features originate; downstream refers to derivative distributions that consume and refine those upstream changes[cite: 1].
* **Fedora Linux:** The rapid-innovation upstream distro where new ideas and open-source tech are combined[cite: 1].
* **CentOS Stream:** A continuously delivered distribution that serves as the upstream preview for the next minor release of RHEL[cite: 1].
* **RHEL (Red Hat Enterprise Linux):** Red Hat's production-grade, highly predictable, fully supported enterprise distribution[cite: 1].
* **Package Manager:** A tool that automates installing, updating, configuring, and removing software packages[cite: 1].
* **RPM (Red Hat Package Manager):** The core package management file format and tool used across RHEL, CentOS Stream, and Fedora[cite: 1].
* **FHS (Filesystem Hierarchy Standard):** A standardized directory structure definition for Unix-like systems ensuring predictable file locations[cite: 1].
* **Leapp:** The official command-line tool used to perform in-place major upgrades between RHEL versions[cite: 1].

## Commands Learnt
*(Note: No executable terminal commands were directly executed in this theory lesson, but key system tools were introduced.)*
* **RPM (`rpm`):** Package management engine used across RHEL, CentOS Stream, and Fedora[cite: 1].
* **Leapp (`leapp`):** System utility used for executing major-version upgrades on RHEL systems[cite: 1].

## Key Concepts

### 1. The Red Hat Ecosystem Pipeline
The flow of code moves from community innovation to enterprise stability:
1. **Open Source Community Projects:** Independent projects developing raw features[cite: 1].
2. **Fedora Linux:** Integrates community innovation into a fast-moving, cutting-edge distribution[cite: 1].
3. **CentOS Stream:** Acts as a rolling preview channel for upcoming RHEL minor releases, allowing developers to contribute directly to RHEL's future[cite: 1].
4. **Red Hat Enterprise Linux (RHEL):** Production-ready OS optimized for security, predictability, and critical enterprise workloads[cite: 1].

### 2. Deep Dive: Filesystem Hierarchy Standard (FHS)
Red Hat adheres strictly to the FHS, which defines where files and directories must reside[cite: 1]. This consistency makes administration and troubleshooting predictable across systems[cite: 1]:
* `/bin` & `/sbin`: Essential user commands (`/bin`) and system administration commands (`/sbin`).
* `/etc`: System-wide configuration files.
* `/var`: Variable data files (e.g., system logs at `/var/log`, databases, mail spools).
* `/usr`: Secondary hierarchy containing user utilities and applications.
* `/home`: Personal directories for regular users.
* `/root`: Home directory for the administrative `root` superuser.

### 3. RHEL Lifecycle & Support Model
RHEL provides a 10-year lifecycle per major release, with new major versions released every 3 years[cite: 1]:
* **Full Support Phase (Years 1–5):** Full bug fixes, security updates, software enhancements, and hardware enablement[cite: 1].
* **Maintenance Support Phase (Years 6–10):** Focuses primarily on critical security patches and high-severity bug fixes[cite: 1].
* **Extended Update Support (EUS):** Extended coverage option for critical security patches after primary phases conclude[cite: 1].

### 4. No-Cost Developer Subscription
Red Hat provides a free Individual Developer Subscription allowing up to 16 production or non-production systems with full updates and self-service support[cite: 1].

## Main Notes
* Red Hat actively authors and contributes back to core Linux technologies, including **systemd** (system and service manager), **KVM** (Kernel-based Virtual Machine for virtualization), and **TuneD** (adaptive system tuning daemon)[cite: 1].
* RPM packages are distinct from Debian-based `.deb` packages and cannot be directly installed via Debian's `apt` package manager without conversion tools[cite: 1].

## My Key Learning
Red Hat's strength is its predictability and strict adherence to open standards (like FHS)[cite: 1]. The progression from Fedora to CentOS Stream to RHEL shows how open-source innovation is systematically battle-tested before entering enterprise production environments[cite: 1].