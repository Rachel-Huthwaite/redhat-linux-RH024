# 17 - Managing Systems with RHEL Web Console

## Overall Summary
This lesson introduces the RHEL Web Console, powered by the open-source **Cockpit** project. Cockpit provides an intuitive, browser-based graphical user interface (GUI) for system administration on Red Hat Enterprise Linux, making administrative tasks accessible from any desktop or mobile browser. Crucially, Cockpit does not introduce proprietary APIs or backdoors; instead, it executes standard underlying RHEL CLI tools and APIs directly under the hood. The lesson details service enablement on port `9090`, system privilege escalation (equivalent to `sudo -i`), comprehensive navigation across main dashboard pages (Overview, Logs, Storage, Networking, Podman Containers, Virtual Machines, Accounts, Services, Session Recording), and extending Cockpit capabilities using `cockpit-*` plugin packages.

## New Jargon
* **Cockpit / RHEL Web Console:** A browser-based server administration tool for Linux that provides a graphical dashboard for monitoring and managing system components directly over web sockets.
* **`cockpit.socket`:** The `systemd` socket unit listening on port `9090` that activates the Cockpit web interface dynamically upon receiving incoming connection requests.
* **Privileged Mode ("Turn on Administrative Access"):** An inline toggle within Cockpit that escalates web session permissions to administrative (`root`) status using `sudo` credentials.
* **Cockpit Plugins:** Modular extension packages (prefixed with `cockpit-*`) that add specialized administration interfaces (e.g., Podman, Virtualization, Session Recording) to the console.

## Commands Learnt
* **`sudo systemctl enable --now cockpit.socket`:** Configures the Cockpit web console socket to start automatically at boot and immediately begins listening for web browser traffic.
* **`dnf search cockpit-*`:** Searches available repositories for Cockpit extension modules and plugin packages.
* **`sudo dnf install -y cockpit-*`:** Installs all available Cockpit plugin extensions non-interactively.

## Key Concepts

### 1. Architectural Philosophy of Cockpit
* **No Secret Backdoors / No Middleman APIs:** Cockpit interacts directly with standard system tools (`systemd`, `StorageManager`, `nmcli`, `podman`, `libvirt`). Changes made in Cockpit are identical to executing equivalent terminal commands.
* **Lightweight Execution:** Cockpit consumes zero RAM or CPU resources when no administrator is logged into the web interface.
* **Mobile & Browser Access:** Accessible over TLS at `https://<hostname-or-ip>:9090` across modern desktop and mobile browsers.

---

### 2. Deep Dive: Dashboard Breakdown & Interface Navigation

#### Accessing the Console
Enable the socket and navigate to the server URL:
```bash
sudo systemctl enable --now cockpit.socket
```

Open `https://rhel10:9090` in a web browser. Upon logging in, click **"Turn on Administrative Access"** in the top navigation bar to gain full `root` privilege escalation (equivalent to `sudo -i`).

#### Page-by-Page Feature Breakdown

* **Overview Page:**
  Features four core operational blocks:
  1. **Health:** Highlights system alerts, hardware warnings, or failing services.
  2. **Usage:** Real-time visual graphs monitoring CPU utilization, memory consumption, disk I/O, and network throughput.
  3. **System Information:** Displays hostname, hardware vendor, system architecture, operating system version (e.g., RHEL 10), and system time[cite: 13].
  4. **Configuration:** Quick links to manage domain membership, system performance profiles (`tuned`), and system reboot/shutdown actions[cite: 13].

* **Logs Page:**
  Interacts directly with `journalctl`[cite: 13].
  * **Boot Selector:** Dropdown filtering logs by specific boot sessions (e.g., *Current Boot*, *Previous Boot*)[cite: 13].
  * **Priority Filter:** Dropdown filtering entries by severity levels (*Emergency*, *Alert*, *Critical*, *Error*, *Warning*, *Notice*, *Info*, *Debug*)[cite: 13].
  * **Search & Time Range:** Real-time text search and custom date range filters[cite: 13].

* **Storage Page:**
  Provides full graphical disk and filesystem management[cite: 13].
  * Visualizes reading/writing performance graphs[cite: 13].
  * Displays physical drives, partition tables, LVM (Logical Volume Manager) volume groups, logical volumes, and software RAID arrays[cite: 13].
  * Allows creating, formatting, expanding, mounting, and unmounting filesystems (XFS, EXT4), alongside NFS mount configuration[cite: 13].

* **Networking Page:**
  Interacts with NetworkManager (`nmcli`)[cite: 13].
  * Displays active physical interfaces, traffic graphs (send/receive rates), and active IP/MAC addresses[cite: 13].
  * Supports creating network bonds, bridges, VLANs, and editing firewall rules (`firewalld`) directly[cite: 13].

* **Podman Containers Page (`cockpit-podman`):**
  Graphical container management interface[cite: 13].
  * Lists running and stopped containers, container images, and pods[cite: 13].
  * Supports pulling images from registries, running new containers, configuring port mappings/volume mounts, and viewing live container logs or opening interactive container shell terminals[cite: 13].

* **Virtual Machines Page (`cockpit-machines`):**
  Integrates with `libvirt` / KVM virtualization[cite: 13].
  * Displays managed virtual machines, active memory/CPU allocation, and hypervisor storage pools[cite: 13].
  * Allows creating VMs from ISOs/cloud images, performing start/stop/pause operations, taking snapshots, and launching embedded VNC/SPICE graphical guest consoles[cite: 13].

* **Accounts Page:**
  User and group administration[cite: 13].
  * Lists local user accounts, locking/unlocking users, changing passwords, enforcing password expiration policies, adding SSH public keys, and granting `sudo` administrative rights[cite: 13].

* **Services Page:**
  Direct graphical interface to `systemd`[cite: 13].
  * Categorized tabs: *Services*, *Sockets*, *Targets*, *Timers*, *Paths*[cite: 13].
  * Searchable list showing execution state (`running`, `stopped`) and boot state (`enabled`, `disabled`)[cite: 13].
  * Supports starting, stopping, restarting, enabling, and disabling units with single-click actions[cite: 13].

* **Session Recording Page (`cockpit-session-recording`):**
  Integrates with `tlog` and SSSD for security compliance[cite: 13].
  * Allows security auditors and sysadmins to play back video-like terminal recordings of user interactive SSH or Cockpit terminal sessions[cite: 13].

---

### 3. Extending Cockpit with Plugins
To discover and install modular extension plugins[cite: 13]:
```bash
dnf search cockpit-*
sudo dnf install -y cockpit-*
```

Installing cockpit-* automatically adds dedicated management tabs (such as Podman, Virtual Machines, or Session Recording) directly into the Cockpit side navigation sidebar[cite: 13].

### Main Notes

* Cockpit does not replace CLI tools; it simply exposes standard RHEL tools visually, ensuring no configuration conflicts between CLI and GUI administration[cite: 13].

* Enabling cockpit.socket ensures port 9090 listens on demand, avoiding unnecessary background system memory usage until a user accesses the URL[cite: 13].

### My Key Learning

The RHEL Web Console (Cockpit) bridges visual administration with enterprise CLI tools[cite: 13]. Because it executes standard RHEL commands and APIs under the hood without introducing hidden layers, sysadmins can monitor metrics, inspect logs, control services, manage storage, and run containers seamlessly from any browser[cite: 13].