# 06 - Basic File Management

## Overall Summary
This lesson covers essential command-line file management operations, detailing how to create, move, copy, rename, and delete files and directories directly within the shell[cite: 6]. It explores detailed directory listings using `ls` flags (`-l`, `-h`, `-a`)[cite: 6] and safe file manipulation techniques, such as using interactive confirmation (`-i`) to prevent accidental deletion during recursive directory removal[cite: 6].

## New Jargon
* **Hidden File:** Files or directories whose names begin with a period (`.`) that are hidden from standard listings by default[cite: 6].
* **Long Listing Format (`ls -l`):** A detailed directory listing display showing file permissions, ownership, size, modification dates, and file names[cite: 6].
* **Recursive Operation (`-r` / `-R`):** An operation applied sequentially down a directory tree, affecting the directory and all contained subdirectories and files[cite: 6].
* **Verbose Flag (`-v`):** An option flag that causes commands to print explicit, real-time output explaining what actions are being performed[cite: 6].
* **Interactive Flag (`-i`):** A protective flag that forces commands (like `rm` or `cp`) to prompt for user confirmation before overwriting or removing files[cite: 6].

## Commands Learnt
* **`ls` (List Directory):**
  * `ls -l`: Displays directory contents in a detailed long-listing format[cite: 6].
  * `ls -lh`: Displays file sizes in human-readable units (e.g., KB, MB, GB)[cite: 6].
  * `ls -lha`: Displays long listing format including human-readable sizes and hidden files[cite: 6].
* **`mkdir` (Make Directory):** Creates new directories[cite: 6].
  * `mkdir -p`: Parent flag; creates parent directories as needed without throwing an error if the directory already exists[cite: 6].
  * `mkdir -pv`: Parent + Verbose flag; creates nested parent directory paths and outputs a message confirming each directory created[cite: 6].
* **`touch`:** Creates an empty file or updates the access/modification timestamps of an existing file[cite: 6].
* **`cp` (Copy):** Copies files or directories from a source to a destination[cite: 6].
* **`mv` (Move / Rename):** Moves files to a different directory or renames a file if destination is in the same directory path[cite: 6].
* **`rm` (Remove):** Deletes files[cite: 6].
  * `rm -r`: Recursively deletes a directory and all of its contents[cite: 6].
  * `rm -i`: Interactively prompts for confirmation before deleting each file[cite: 6].
  * `rm -ri`: Combines recursive directory deletion with interactive safety prompts[cite: 6].

## Key Concepts

### 1. Advanced Directory Listing Combinations
Combining flags in `ls` provides precise metadata[cite: 6]:
* `-l` provides permissions, link count, owner, group, size (in bytes), timestamp, and name[cite: 6].
* `-h` converts raw byte outputs into human-readable numbers[cite: 6].
* `-a` exposes hidden configuration files (e.g., `.bashrc`)[cite: 6].

### 2. File and Directory Operations
* **Renaming vs. Moving with `mv`:** `mv` performs both tasks[cite: 6]. If the destination path is a directory, the file is moved[cite: 6]. If the destination path is a new filename in the same directory, the file is renamed[cite: 6].
* **Parent Directory Creation with `mkdir -p`:** Allows creation of entire directory trees in a single command (e.g., `mkdir -p project/src/components`)[cite: 6].

### 3. Deletion Safeguards
Recursive deletions (`rm -r`) permanently destroy directory trees[cite: 6]. Combining interactive prompts (`rm -ri`) ensures every file deletion requires manual confirmation (`y/n`), providing a safeguard against devastating command-line accidents[cite: 6].

### 4. Deep Dive: Terminal Speed vs. GUI Efficiency
While graphical file managers require manual mouse movements and visual searching, terminal workflows allow scripting, wildcard expansion, and bulk manipulation that scale far beyond GUI limits[cite: 6]:
* **Research Insights:** Ergonomic and operational speed studies (such as GOMS/Keystroke-Level Model evaluations) show that trained command-line users complete repetitive file management tasks significantly faster than GUI users. This advantage stems from eliminating pointing device acquisition times and leveraging shell automation features like loops, pipes, and wildcards.

## Main Notes
* Hidden files always begin with a dot (`.`)[cite: 6].
* `touch` is the standard tool for quickly creating empty placeholder files[cite: 6].

## My Key Learning
Combining options like `mkdir -pv` and `rm -ri` provides immediate feedback and essential safety nets, making terminal file operations both faster and less error-prone than graphical interfaces[cite: 6].