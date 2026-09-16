# 12 - Managing System Startup Services with systemd

## Overall Summary
This lesson covers Linux service and process management using `systemd`, the standard init system across modern Linux distributions. It breaks down how `systemd` manages system startup, execution order, and background processes using various unit types (service, socket, timer, path, target). The lesson provides a step-by-step walkthrough of deploying an Apache (`httpd`) web server, managing service states using `systemctl`, configuring persistent firewalls via `firewall-cmd`, and utilizing bash history expansion shortcuts (`!!` and `^search^replace`).

## New Jargon
* **`systemd`:** The default system and service manager for Linux that initializes the user space, manages background daemons, and handles event-based activations.
* **Daemon:** A non-interactive background process that runs continuously to handle system requests, services, or events (e.g., `httpd`, `sshd`).
* **`systemd` Unit:** An object representation managed by `systemd` that controls system resources or operations.
* **Service Unit (`.service`):** Manages background applications and daemons.
* **Socket Unit (`.socket`):** Facilitates network or IPC communication sockets, enabling on-demand service activation upon incoming traffic.
* **Timer Unit (`.timer`):** Schedules task execution relative to time or events, serving as a modern replacement for `cron`.
* **Path Unit (`.path`):** Monitors specified filesystem paths and triggers an associated service when files/directories are modified.
* **Target Unit (`.target`):** Logically groups multiple units together to establish system state execution runlevels (e.g., `multi-user.target`).

## Commands Learnt
* **`dnf install -y httpd`:** Downloads and installs the Apache HTTP web server non-interactively[cite: 10, 12].
* **`echo "hello world" | tee /var/www/html/index.html`:** Writes output to standard output while simultaneously writing to a file.
* **`systemctl start httpd`:** Immediately starts the `httpd` daemon process in the current session[cite: 12].
* **`systemctl enable httpd`:** Configures the `httpd` service to start automatically during system boot[cite: 12].
* **`systemctl enable --now httpd`:** Combines `enable` and `start` into a single operation[cite: 12].
* **`systemctl status httpd`:** Displays active runtime status, process identification (PID), memory usage, and recent logs for the service[cite: 12].
* **`systemctl restart httpd`:** Restarts the running service process[cite: 12].
* **`systemctl stop httpd`:** Halts the running service process immediately[cite: 12].
* **`systemctl disable httpd`:** Removes boot startup autostraint link, preventing startup at boot[cite: 12].
* **`firewall-cmd --add-service=http`:** Temporarily permits HTTP network traffic in the current runtime firewall policy[cite: 12].
* **`firewall-cmd --add-service=http --permanent`:** Writes the firewall exception persistently to disk across reboots[cite: 12].
* **`firewall-cmd --list-all`:** Displays enabled firewall services, ports, and zone configurations[cite: 12].
* **`!!`:** Bash shortcut repeating the exact prior terminal command[cite: 12].
* **`^old^new`:** Quick bash string substitution; re-runs the prior command while replacing the first instance of `old` with `new`[cite: 12].

## Key Concepts

### 1. `systemd` Unit Types
`systemd` categorizes resources into explicit unit types[cite: 12]:
* **`service`:** Runs applications and background daemons[cite: 12].
* **`socket`:** Listens on network ports and activates service daemons on demand[cite: 12].
* **`timer`:** Executes tasks on automated time schedules[cite: 12].
* **`path`:** Triggers actions upon detecting directory or file modifications[cite: 12].
* **`target`:** Coordinates startup dependencies by grouping linked units[cite: 12].

### 2. Complete Walkthrough: Deploying & Securing Apache (`httpd`)

#### Step 1: Software Installation & Content Creation
```bash
dnf install -y httpd
echo "hello world" | tee /var/www/html/index.html
```
Installs Apache web server package and populates default web content[cite: 12].

#### Step 2: Service Enablement & Verification
```bash
systemctl enable --now httpd
systemctl status httpd
```

Enables httpd for automatic system startup, launches the runtime daemon instantly, and verifies active execution state (active (running))[cite: 12].

#### Step 3: Firewall Configuration & History Shortcut Usage

```bash
firewall-cmd --add-service=http
!! --permanent
firewall-cmd --list-all
```

Opens HTTP network port 80 dynamically[cite: 12]. Using !! --permanent re-executes firewall-cmd --add-service=http appended with --permanent to preserve policy across system reboots[cite: 12]. Finally, --list-all confirms network availability[cite: 12].

#### Step 4: Bash Substitution Service Livecyle Control

```bash
systemctl restart httpd
^restart^stop
^stop^disable
```
Using quick substitution shortcuts[cite: 12]:

* ^restart^stop modifies systemctl restart httpd into systemctl stop httpd to halt the process[cite: 12].

* ^stop^disable modifies systemctl stop httpd into systemctl disable httpd to disable startup enablement[cite: 12].
---

### Main Notes

* Using systemctl enable --now reduces service setup overhead by enabling autostart and executing runtime startup in a single step[cite: 12].

* Modifying firewall-cmd parameters without --permanent applies changes strictly to ephemeral runtime memory; always ensure persistent flags are appended for lasting configurations[cite: 12].

### My Key Learning

systemd standardizes service workflows through structured unit types[cite: 12]. Combining systemctl runtime management with persistent firewall adjustments ensures enterprise services operate securely and withstand system reboots[cite: 12].

