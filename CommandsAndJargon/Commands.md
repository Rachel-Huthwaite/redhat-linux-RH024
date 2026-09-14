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