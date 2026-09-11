# 02 - Introduction to Shell

## Overall Summary
This lesson introduces the command-line environment and the shell, which serves as the primary interface for executing commands in Linux[cite: 2]. It covers the basic structure of a command—comprising the command itself, options (flags), and arguments[cite: 2]. The lesson also demonstrates practical command usage with disk space monitoring tools and highlights essential productivity features like Tab autocompletion[cite: 2].

## New Jargon
* **Shell:** A command-line interpreter that takes user inputs, executes commands, and communicates with the underlying operating system kernel[cite: 2].
* **Command:** An executable program or built-in utility run within the shell[cite: 2].
* **Option (Flag):** Modifiers passed to a command to alter its behavior, prefixed with a single dash (`-`) for short options or double dashes (`--`) for long options[cite: 2].
* **Argument:** The target or input data (such as files, directories, or text) that a command acts upon[cite: 2].
* **Tab Autocompletion:** A productivity feature in the shell that automatically completes file paths, directory names, commands, and subcommands when pressing the `Tab` key[cite: 2].

## Commands Learnt
* **`du` (Disk Usage):** Estimates and summarizes file and directory space usage[cite: 2].
  * `du -sh /home/{filename}`: Displays a summary (`-s`) in human-readable units like MB or GB (`-h`) for the specified file or path[cite: 2].

## Key Concepts

### 1. Structure of a Linux Command
A standard shell command is constructed using three primary components[cite: 2]:
* **Command:** The executable program to run (e.g., `du`)[cite: 2].
* **Options:** Controls *how* the command executes[cite: 2]. Options use a single dash for short options (e.g., `-s`, `-h`) or a double dash for long options (e.g., `--human-readable`)[cite: 2]. Multiple short options can often be combined (e.g., `-sh`)[cite: 2].
* **Arguments:** The target that the command acts on (e.g., `/home/user`)[cite: 2].

> **Note:** Commands vary in requirements; some require both options and arguments, others require only one, and many can run with neither depending on their built-in defaults[cite: 2].

### 2. Tab Autocompletion Basics
* **Single Tab:** Completes a uniquely matched command, directory, or file path automatically once enough characters are typed[cite: 2].
* **Double Tab (`Tab` + `Tab`):** Displays all available possibilities when multiple matches exist, or lists available subcommands for supported applications[cite: 2].

### 3. Checking Command Documentation
To determine which options or arguments a command expects, you can inspect its documentation[cite: 2]:
* **`man <command>`:** Displays the official system reference manual page detailing all syntax, options, and descriptions[cite: 2].
* **`tldr <command>`:** Community-driven, practical cheat sheets providing quick examples for common usage scenarios[cite: 2].

## Main Notes
* Understanding command syntax (command + options + arguments) is fundamental to mastering terminal operations[cite: 2].
* Tab completion reduces typing errors and speeds up command navigation significantly[cite: 2].

## My Key Learning
Mastering Tab autocompletion—especially double-tabbing to discover available subcommands and paths—is essential for fast terminal navigation and reducing syntax errors[cite: 2].