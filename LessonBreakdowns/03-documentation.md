# 03 - Documentation

## Overall Summary
This lesson covers Linux documentation, focusing on manual pages (`man` pages) that are built directly into the operating system[cite: 3]. It breaks down how system manual pages are structured, how to use built-in search functionality to locate specific options or keywords, and how to safely exit the viewer[cite: 3]. Beyond system commands, `man` pages also provide detailed documentation for configuration files and even the `man` system itself[cite: 3].

## New Jargon
* **Man Page (Manual Page):** Built-in documentation files available locally on a Linux system that provide reference material for commands, utilities, system functions, and configuration files[cite: 3].
* **In-Page Search:** A navigation feature within the terminal viewer allowing users to search for specific terms using keywords[cite: 3].

## Commands Learnt
* **`man` (Manual):** Displays the system reference manual pages[cite: 3].
  * `man <command>`: Opens the manual page for a command or software tool[cite: 3].
  * `man <config_file>`: Opens the documentation for specific system configuration files[cite: 3].
  * `man man`: Opens the manual page for the `man` utility itself[cite: 3].

## Key Concepts

### 1. Built-in System Documentation
Unlike operating systems that require browsing external web documentation, Linux includes comprehensive reference material stored directly on the local filesystem[cite: 3].

### 2. Navigating and Searching `man` Pages
When viewing a manual page inside the system viewer (`less`):
* **Searching Forward (`/`):** Type `/` followed by a keyword (e.g., `/keyword`) and press `Enter` to find matching occurrences[cite: 3].
* **Next Match (`n`):** Press `n` to jump to the next matching result in the document[cite: 3].
* **Previous Match (`N`):** Press `N` (Shift + `n`) to jump back to the previous match.
* **Exiting (`q`):** Press `q` to close the manual page and return to the terminal prompt[cite: 3].

### 3. Scope of `man` Pages
`man` pages cover more than basic shell executable commands:
* **Executables & Utilities:** Reference pages for terminal commands (e.g., `ls`, `du`, `tar`)[cite: 2, 3].
* **Configuration Files:** Technical syntax and options for system configuration files (e.g., `/etc/fstab` or `/etc/ssh/sshd_config`)[cite: 3].
* **System Tools:** Self-referential help, such as running `man man` to understand manual page section numbering and options[cite: 3].

## Main Notes
* Utilizing local documentation is faster and more reliable than web searches, as local `man` pages match the exact software version installed on the system[cite: 3].

## My Key Learning
System `man` pages extend far beyond basic commands—they also document system configuration file formats, making them an indispensable offline troubleshooting tool[cite: 3].