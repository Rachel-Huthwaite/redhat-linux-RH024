# 05 - Linux Directories Explained

## Overall Summary
This lesson breaks down the Linux directory layout, demonstrating how all files and directories stem from a single root directory (`/`)[cite: 5]. It explains fundamental navigation commands (`pwd`, `cd`, `ls`)[cite: 5] and explores essential system directories defined by the Filesystem Hierarchy Standard[cite: 1, 5], including `/etc`, `/var`, `/tmp`, `/usr`, `/root`, `/boot`, `/mnt`, and `/run`[cite: 5]. It also covers administrative best practices, such as backing up configuration files before making changes[cite: 5].

## New Jargon
* **Root Directory (`/`):** The top-level directory in the Linux directory tree from which all other directories branch[cite: 5].
* **Binary (`/usr/bin`):** Compiled, executable programs or utilities that users run from the command line[cite: 5].
* **Configuration File:** Text files (typically inside `/etc`) that define operational settings and behaviors for system services and applications[cite: 5].
* **Mounting (`/mnt`):** The process of attaching a filesystem or storage device (e.g., secondary hard drives, USB drives, NFS shares) to a specific path in the directory tree so it becomes accessible[cite: 5].
* **Virtual Filesystems (`/proc`, `/sys`, `/dev`):** Special pseudo-filesystems generated dynamically by the kernel to reflect hardware state, system processes, and device files[cite: 5].

## Commands Learnt
* **`pwd` (Print Working Directory):** Outputs the full absolute path of the current working directory[cite: 5].
* **`cd` (Change Directory):** Navigates between system directories[cite: 5].
  * `cd`: Running with no options or arguments automatically returns the user to their personal home directory[cite: 5].
  * `cd <path>`: Changes the current directory to the specified target path[cite: 5].
* **`ls` (List):** Lists contents within a directory[cite: 5].
  * `ls -a`: Lists all entries, including hidden files and directories (those starting with a dot `.`).

## Key Concepts

### 1. The Root Directory Structure (`/`)
Unlike Windows (which uses drive letters like `C:` or `D:`), Linux represents everything as a unified file tree starting at root (`/`)[cite: 5]:

* **`/home`:** Contains individual user home directories (e.g., `/home/username`) where users store personal documents and user-level configuration files[cite: 5].
* **`/etc` (Extended Text Configurations):** System-wide configuration files[cite: 5]. **Best Practice:** Always create a backup copy of any configuration file before modifying it (e.g., `cp config.conf config.conf.bak`)[cite: 5].
* **`/usr` (User System Resources):** Holds user utilities, libraries, and shared assets[cite: 5]:
  * `/usr/bin`: Primary directory for executable binary programs[cite: 5].
  * `/usr/lib64`: Shared 64-bit library files required by executable binaries[cite: 5].
  * `/usr/share`: Architecture-independent shared data (such as documentation, icons, and themes)[cite: 5].
* **`/root`:** The specialized home directory for the `root` administrative superuser, accessible only with elevated permissions[cite: 5].
* **`/boot`:** Contains files required to boot the operating system, including the Linux Kernel and bootloader configuration[cite: 5]. Typically accessed when diagnosing boot failures[cite: 5].

### 2. Deep Dive: `/tmp` vs `/var`
Both directories manage dynamic data, but they serve different persistence and security roles[cite: 5]:
* **`/tmp` (Temporary Files):** 
  * Designed for transient, short-term scratch storage used by applications during operation[cite: 5].
  * Automatically purged by the system periodically or on reboot[cite: 5].
  * World-writable: Never place sensitive files in `/tmp` because all local system users have read access[cite: 5].
  * *Example:* A video editor generating temporary render cache frames while exporting.
* **`/var` (Variable Data):** 
  * Intended for data that grows dynamically over time and must persist across reboots[cite: 5].
  * *Examples:* System logs (`/var/log`), database files (`/var/lib/mysql`), and printer/mail spools (`/var/spool`)[cite: 1, 5].

### 3. Deep Dive: Mount Points (`/mnt`)
* Mounting binds a physical or network storage device to a directory location in the tree[cite: 5].
* `/mnt` acts as a temporary mount point location for administrators to attach external hard drives, ISO images, or network shares (e.g., NFS)[cite: 5].

### 4. Ephemeral & System Directories
* **`/run`:** A volatile memory-backed directory (tmpfs) that tracks real-time runtime state data (e.g., process ID files, socket files)[cite: 5]. Recreated completely fresh upon every boot[cite: 5].
* **`/proc`, `/sys`, `/dev`:** Kernel internals and device mapping files; non-essential for daily operations when getting started, but crucial for low-level system troubleshooting[cite: 5].

## Main Notes
* Always print your working directory (`pwd`) when performing administrative tasks to confirm your location before modifying or deleting files[cite: 5].
* backing up `/etc` files before editing prevents system misconfigurations from becoming breaking failures[cite: 5].

## My Key Learning
Understanding directory roles removes the mystery of Linux troubleshooting[cite: 5]. Realizing that system-wide software settings reside in readable text files under `/etc` makes locating and fixing broken configurations straightforward[cite: 5].