# Technical Dictionary & Jargon

### CentOS Stream
A continuously delivered Linux distribution that serves as the upstream development target for upcoming RHEL minor releases, bridging the gap between Fedora and RHEL[cite: 1].

### Fedora Linux
A community-driven, rapid-innovation Linux distribution sponsored by Red Hat, serving as the proving ground for emerging technologies and open-source software[cite: 1].

### Filesystem Hierarchy Standard (FHS)
A reference standard defining the structure and directory layout of Unix and Linux operating systems to ensure consistency across distributions[cite: 1].

### KVM (Kernel-based Virtual Machine)
An open-source virtualization module built into the Linux kernel that allows the system to function as a hypervisor[cite: 1].

### Leapp
Red Hat's official upgrade framework designed to analyze system readiness and execute seamless major-version system upgrades (e.g., RHEL 8 to RHEL 9)[cite: 1].

### Linux Distribution (Distro)
An operating system constructed from the Linux Kernel, bundled with essential user utilities, software managers, desktop environments, and configuration files[cite: 1].

### Linux Kernel
The core component of a Linux operating system that manages hardware resources (CPU, memory, devices) and acts as an abstraction layer between hardware and applications[cite: 1].

### Package Manager
A software suite that automates the installation, upgrading, dependency resolution, configuration, and removal of computer programs[cite: 1].

### RHEL (Red Hat Enterprise Linux)
Red Hat’s commercial, enterprise-grade Linux distribution built for stability, security, and long-term production support[cite: 1].

### RPM (Red Hat Package Manager)
The underlying software packaging format and low-level package installation tool used across Red Hat ecosystem distributions[cite: 1].

### systemd
An init system and system manager for Linux operating systems that bootstraps the user space and manages system processes and services[cite: 1].

### TuneD
A dynamic adaptive tuning daemon that monitors system usage and optimizes performance based on pre-defined workload profiles[cite: 1].

### Argument
The target input (such as a path, file name, or variable) provided to a command for it to operate on[cite: 2].

### Command
An executable binary, shell script, or built-in utility run inside the terminal[cite: 2].

### Option (Flag)
A parameter passed to a command that modifies its execution behavior, formatted with a single dash (`-`) for short options or double dashes (`--`) for long options[cite: 2].

### Shell
A command-line program that accepts keyboard input, translates commands, and passes them to the operating system kernel to execute[cite: 2].

### Tab Autocompletion
A shell feature that automatically completes typed commands, directory names, and file paths when the `Tab` key is pressed[cite: 2].

### In-Page Search
A navigation capability within terminal text viewers (like `less`) that lets users query text forward using `/` and cycle through results using `n`[cite: 3].

### Man Page
A built-in system documentation file providing reference information, syntax breakdowns, and option lists for commands, system calls, and configuration files[cite: 3].

### Red Hat Satellite
An enterprise management platform that locally mirrors Red Hat software repositories, automates system provisioning, and controls patch lifecycle stages across enterprise networks[cite: 4].

### Repository Mirroring
The process of maintaining a local synchronization of remote software repositories, allowing internal systems to download updates without direct internet connectivity[cite: 4].

### RHEL Lightspeed
Red Hat's integrated AI technology designed to assist system administrators with real-time guidance, command generation, and troubleshooting directly within the operating system[cite: 4].

### System Registration
The administrative task of linking a RHEL installation to Red Hat Subscription Management or Red Hat Satellite to authorize access to system updates and cloud services[cite: 4].

### Binary (`/usr/bin`)
An executable file compiled into machine code that the system can run directly[cite: 5].

### Configuration File (`/etc`)
A plain-text file containing parameter settings that govern software behavior and system configuration[cite: 5].

### Mounting (`/mnt`)
The process of linking a storage device's filesystem to a specific directory path within the Linux root hierarchy[cite: 5].

### Root Directory (`/`)
The base level of the Linux filesystem hierarchy from which all paths originate[cite: 5].

### Temporary Storage (`/tmp`)
A system-cleared, public-writable folder used for non-essential temporary data[cite: 5].

### Variable Data (`/var`)
A persistent directory designated for files that continuously change size during normal operation, such as log files and databases[cite: 1, 5].

### Hidden File
A file or directory name that starts with a dot (`.`), making it invisible to standard listing commands unless the `-a` flag is used[cite: 6].

### Interactive Flag (`-i`)
A protection option passed to administrative commands that prompts the user for explicit confirmation before altering or deleting data[cite: 6].

### Long Listing Format
A detailed output mode for file listings that displays file permissions, ownership details, sizes, and timestamps[cite: 6].

### Recursive Operation (`-r`)
A command execution mode that traverses down through parent directories and all nested subdirectories[cite: 6].

### Verbose Flag (`-v`)
A parameter that forces a command to output detailed operational feedback about each action it completes[cite: 6].

### Command Mode (Ex Mode)
A Vim mode entered by pressing `:` in Normal mode, allowing users to run file operations such as saving (`:w`) or quitting (`:q`)[cite: 7].

### Insert Mode
The Vim editing mode entered by pressing `i`, which allows inputting characters directly into the document[cite: 7].

### Modal Editing
A user interface design where key presses have different behaviors based on the active operational state (mode)[cite: 7].

### Normal Mode
The primary navigation state of Vim where keyboard inputs trigger movement, copy, paste, and deletion shortcuts[cite: 7].

### Vim
A lightweight, fast, terminal-based text editor included by default across Linux distributions[cite: 7].

### vimtutor
An interactive built-in terminal tutorial designed for practicing core Vim keyboard controls[cite: 7].

### GID (Group Identifier)
A unique numerical identification number assigned to a system group in `/etc/group`[cite: 8].

### Local User Account
A user profile defined directly within a local machine's `/etc/passwd` and `/etc/shadow` files[cite: 8].

### Orphan File
A file whose stored owner UID does not match any currently active user account on the system[cite: 8].

### Red Hat IdM (Identity Management)
A centralized enterprise identity management platform provided by Red Hat to manage users, groups, host access, and authentication centrally[cite: 8].

### UID (User Identifier)
A unique numerical identification number assigned to each user account that the Linux kernel uses for access control[cite: 8].

### wheel Group
A default administrative group in RHEL whose members are granted administrative command access via `sudo`[cite: 8].

### Absolute Permission Mode
A method of defining permissions using 3-digit octal notation (0-7), where each digit represents the sum of Read (4), Write (2), and Execute (1)[cite: 9].

### File Permissions
An access control system in Linux that defines Read (`r`), Write (`w`), and Execute (`x`) rights for Owner, Group, and Others[cite: 9].

### Octal Notation
A base-8 numerical system used in Linux permission management where values 4, 2, and 1 correspond to read, write, and execute permissions[cite: 9].

### Principle of Least Privilege
A security strategy requiring that user accounts and services are granted only the essential permissions needed to perform their tasks[cite: 9].

### tmux
A terminal window manager and multiplexer that enables users to manage multiple terminal sessions and keep background jobs alive across SSH disconnects[cite: 9].

### CVE (Common Vulnerabilities and Exposures)
A standardized, publicly tracked reference number assigned to security vulnerabilities[cite: 10].

### CVSS (Common Vulnerability Scoring System)
An open industry standard framework ranging from 0.0 to 10.0 used to assess the severity of security vulnerabilities[cite: 10].

### DNF (Dandified YUM)
The default package manager in Red Hat Enterprise Linux responsible for package installation, dependency management, and system updates[cite: 1, 10].

### Errata
Official Red Hat advisories detailing software bug fixes, security patches, or feature enhancements[cite: 10].

### RHBA (Red Hat Bug Advisory)
A type of Errata advisory released to address non-security software bugs and operational issues[cite: 10].

### RHEA (Red Hat Enhancement Advisory)
An Errata advisory introducing feature updates, enhancements, or new capabilities[cite: 10].

### RHSA (Red Hat Security Advisory)
An Errata advisory addressing security vulnerabilities, categorized by severity levels[cite: 10].

### Network Interface
A system representation of a physical or virtual network device (e.g., `eth0`, `enp7s0`)[cite: 11].

### Network Profile
A collection of stored configuration settings (IP address, subnet, gateway, DNS) managed by NetworkManager[cite: 11].

### nmcli
The primary command-line tool for controlling NetworkManager and modifying network connection profiles[cite: 11].

### nmtui
An interactive terminal interface tool providing a graphical-style menu for managing network profiles[cite: 11].