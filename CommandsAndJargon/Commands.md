# Commands Master List

| Command | Description | Source Lesson |
|---------|-------------|---------------|
| `rpm` | Package management tool used to install, verify, and query software packages on RHEL, Fedora, and CentOS[cite: 1]. | 01 - Linux Distributions |
| `leapp` | Utility for assessing and executing major version in-place upgrades on Red Hat Enterprise Linux[cite: 1]. | 01 - Linux Distributions |
| `du` | Estimates and displays disk space usage for files and directories[cite: 2]. | 02 - Introduction to Shell |
| `man` | Displays the system manual pages for a given command or utility[cite: 2]. | 02 - Introduction to Shell |
| `man` | Formats and displays built-in system reference manual pages for commands, utilities, and configuration files[cite: 3]. | 03 - Documentation |
| `c chat` | Interacts with RHEL Lightspeed AI assistant directly from the command line interface[cite: 4]. | 04 - Command Line Assistant |
| `rhc connect` | Registers a RHEL system to Red Hat Insights and Subscription Management[cite: 4]. | 04 - Command Line Assistant |
| `subscription-manager` | Manages Red Hat subscriptions, system registration, and repository access[cite: 4]. | 04 - Command Line Assistant |
| `pwd` | Displays the absolute path of the current working directory[cite: 5]. | 05 - Linux Directories Explained |
| `cd` | Changes the current working directory (returns to home directory if run without arguments)[cite: 5]. | 05 - Linux Directories Explained |
| `ls` | Lists directory contents (use `-a` to show hidden files)[cite: 5]. | 05 - Linux Directories Explained |
| `ls` | Lists files with flags like `-l` (long listing), `-h` (human readable sizes), and `-a` (show hidden files)[cite: 6]. | 06 - Basic File Management |
| `mkdir` | Creates directories; `-p` builds parent paths and avoids errors, `-v` adds verbose confirmation output[cite: 6]. | 06 - Basic File Management |
| `touch` | Creates an empty file or updates file timestamps[cite: 6]. | 06 - Basic File Management |
| `cp` | Copies files or directories to a specified destination[cite: 6]. | 06 - Basic File Management |
| `mv` | Moves files between directories or renames files in place[cite: 6]. | 06 - Basic File Management |
| `rm` | Removes files; `-r` enables recursive directory removal and `-i` prompts interactively before deletion[cite: 6]. | 06 - Basic File Management |
| `vim` | Opens the terminal-based text editor for creating or modifying files[cite: 7]. | 07 - Editing Files with Vim |
| `vimtutor` | Launches an interactive command-line tutorial for learning Vim keybindings[cite: 7]. | 07 - Editing Files with Vim |
| `cat /etc/passwd` | Outputs local user account configuration database records[cite: 8]. | 08 - Organizing Local Users and Groups |
| `sudo` | Executes commands with elevated root security privileges[cite: 8]. | 08 - Organizing Local Users and Groups |
| `sudo -i` | Opens an interactive root shell using the caller's password[cite: 8]. | 08 - Organizing Local Users and Groups |
| `useradd` | Creates a new system user account[cite: 8]. | 08 - Organizing Local Users and Groups |
| `passwd` | Sets passwords (`passwd <user>`), locks accounts (`-l`), or unlocks accounts (`-u`)[cite: 8]. | 08 - Organizing Local Users and Groups |
| `usermod` | Modifies user attributes like shell (`-s`) or appends secondary groups (`-aG`)[cite: 8]. | 08 - Organizing Local Users and Groups |
| `userdel` | Removes a user account; use `-r` to recursively remove the user's home directory[cite: 8]. | 08 - Organizing Local Users and Groups |
| `groupadd` | Creates a new system group[cite: 8]. | 08 - Organizing Local Users and Groups |
| `groupmod` | Modifies group attributes such as renaming (`-n`)[cite: 8]. | 08 - Organizing Local Users and Groups |
| `groupdel` | Deletes a system group[cite: 8]. | 08 - Organizing Local Users and Groups |
| `id` | Displays numerical UID, primary GID, and secondary group memberships for a user[cite: 8]. | 08 - Organizing Local Users and Groups |
| `groups` | Displays all group names that a user belongs to[cite: 8]. | 08 - Organizing Local Users and Groups |
| `find / -uid <UID> 2>/dev/null` | Searches filesystem for files owned by a specific UID while suppressing permission errors[cite: 8]. | 08 - Organizing Local Users and Groups |
| `su -` | Switches to the root superuser account requiring the root password[cite: 8]. | 08 - Organizing Local Users and Groups |
| `ls -ld` | Displays permissions and ownership details for a directory itself rather than its contents[cite: 9]. | 09 - File Permissions |
| `chmod` | Alters file and directory permission bits using numeric octal codes or symbolic expressions[cite: 9]. | 09 - File Permissions |
| `chown` | Modifies file or directory user and group ownership[cite: 9]. | 09 - File Permissions |
| `tmux` | Starts a terminal multiplexer to run detached, persistent command sessions[cite: 9]. | 09 - File Permissions |
| `subscription-manager identity` | Displays current registration status and identity credentials for Red Hat Subscription Management[cite: 10]. | 10 - Managing Software and Updates |
| `subscription-manager register` | Registers a RHEL host system with Red Hat Subscription Management[cite: 10]. | 10 - Managing Software and Updates |
| `dnf search` | Searches package names and descriptions within enabled software repositories[cite: 10]. | 10 - Managing Software and Updates |
| `dnf install` | Installs specified software packages and required dependencies; `-y` bypasses interactive prompts[cite: 10]. | 10 - Managing Software and Updates |
| `dnf updateinfo list` | Displays available Errata advisories affecting installed system packages[cite: 10]. | 10 - Managing Software and Updates |
| `dnf updateinfo` | Displays detailed metadata breakdown for a specified Errata advisory or file[cite: 10]. | 10 - Managing Software and Updates |
| `dnf update` | Updates all installed packages or a specified package to the latest repository versions[cite: 10]. | 10 - Managing Software and Updates |
| `dnf update --sec-severity=` | Filters system updates to apply only patches matching specified security severity levels[cite: 10]. | 10 - Managing Software and Updates |
| `dnf needs-restarting -r` | Checks whether updated system components require a full operating system reboot[cite: 10]. | 10 - Managing Software and Updates |
| `reboot` | Restarts the system kernel and operating system session[cite: 10]. | 10 - Managing Software and Updates |
| `nmcli con show` | Displays all NetworkManager connection profiles[cite: 11]. | 11 - Managing Networking |
| `ip a s` | Displays IP addresses, status, and subnets for all network interfaces[cite: 11]. | 11 - Managing Networking |
| `ip r s` | Displays kernel IPv4 routing table entries, including default gateways[cite: 11]. | 11 - Managing Networking |
| `cat /etc/resolv.conf` | Displays active system DNS nameserver addresses[cite: 11]. | 11 - Managing Networking |
| `nmcli connection add` | Configures and creates new network connection profiles[cite: 11]. | 11 - Managing Networking |
| `nmcli con del` | Deletes a specified network connection profile[cite: 11]. | 11 - Managing Networking |
| `nmtui` | Launches an interactive text user interface for network profile creation and modification[cite: 11]. | 11 - Managing Networking |
| `systemctl start` | Immediately activates a systemd service daemon in runtime memory[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl enable` | Registers a systemd service unit to launch automatically at boot[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl enable --now` | Simultaneously enables service autostart and launches the daemon immediately[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl status` | Displays execution state, operational logs, PID, and health status for a service unit[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl restart` | Stops and immediately restarts a running systemd service unit[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl stop` | Immediately terminates a running systemd service process[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `systemctl disable` | Unregisters a service unit to prevent automatic execution during system boot[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `firewall-cmd --add-service` | Opens firewall ports corresponding to specified service protocols[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `firewall-cmd --list-all` | Outputs current active zone rules, services, and port permissions[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `!!` | Bash shortcut re-executing the previous line command string[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `^old^new` | Quick bash substitution shortcut replacing target text `old` with `new` in previous command[cite: 12]. | 12 - Managing System Startup Services with systemd |
| `sudo cp <file> /etc/systemd/system/` | Installs a custom systemd unit file into the local system management directory[cite: 14]. | 13 - Deploying an Application Runtime |
| `sudo systemctl daemon-reload` | Forces systemd to reload its unit file configuration index from disk[cite: 14]. | 13 - Deploying an Application Runtime |
| `sudo firewall-cmd --add-port=` | Opens a specific TCP or UDP network port in the firewall runtime configuration[cite: 14]. | 13 - Deploying an Application Runtime |
| `bootc status` | Displays the current deployment status, active boot image, and staged updates on a bootc system[cite: 15]. | 14 - Using Image Mode with Bootc |
| `bootc switch` | Stages a new bootable container image from a remote registry for the next system boot[cite: 15]. | 14 - Using Image Mode with Bootc |
| `rpm -q` | Queries the host RPM database to check for package installation[cite: 15]. | 14 - Using Image Mode with Bootc |