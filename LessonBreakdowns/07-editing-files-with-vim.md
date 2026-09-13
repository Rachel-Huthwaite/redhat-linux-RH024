# 07 - Editing Files with Vim

## Overall Summary
This lesson covers basic text editing using Vim, a light and fast terminal-based text editor built into almost every Linux distribution[cite: 7]. It details how to launch Vim and explains the operational modes: Normal mode, Insert mode, and Command mode[cite: 7]. The lesson also reviews basic text manipulation shortcuts (copying, pasting, undoing, redoing) and key exit commands (`:w`, `:q!`), concluding with an introduction to `vimtutor` for interactive practice[cite: 7].

## New Jargon
* **Vim (Vi Improved):** A highly efficient, modal terminal text editor available by default on Linux systems[cite: 7].
* **Modal Editing:** An editing design where keys perform different functions depending on the current active mode[cite: 7].
* **Normal Mode:** The default navigation and command execution mode in Vim[cite: 7].
* **Insert Mode:** The text input mode where typed characters are written directly into the file[cite: 7].
* **Command Mode (Command-Line / Ex Mode):** The mode used to enter editor commands such as saving, quitting, or running system operations[cite: 7].
* **`vimtutor`:** An interactive built-in tutorial utility designed to teach basic Vim commands through hands-on terminal exercises[cite: 7].

## Commands Learnt
* **`vim`:** Opens the Vim editor[cite: 7].
  * `vim filename.txt`: Opens or creates `filename.txt` in Vim[cite: 7].
* **`vimtutor`:** Launches the interactive Vim terminal tutorial[cite: 7].

## Key Concepts

### 1. The Three Primary Modes of Vim
Vim operates using distinct modes[cite: 7]:
* **Normal Mode (Default):** 
  * Active upon starting Vim[cite: 7].
  * Used for navigating text, deleting lines, copying, and running keyboard shortcuts[cite: 7].
  * Return to Normal mode from any other mode by pressing `Esc`[cite: 7].
* **Insert Mode:** 
  * Entered by pressing `i` while in Normal mode[cite: 7].
  * Displays `-- INSERT --` in the bottom-left corner of the terminal[cite: 7].
  * Allows normal typing of text into the document[cite: 7].
* **Command Mode:** 
  * Entered by typing a colon (`:`) while in Normal mode[cite: 7].
  * Displays a `:` prompt at the bottom-left of the screen[cite: 7].
  * Used to execute commands like saving (`:w`), quitting (`:q`), force quitting without saving (`:q!`), or save-and-quit (`:wq`)[cite: 7].

### 2. Common Keyboard Shortcuts in Normal Mode
* **`yy` (Yank Yearn/Line):** Copies the current line[cite: 7].
* **`p` (Put):** Pastes copied text below the current cursor position[cite: 7].
* **`10p`:** Pastes the copied line 10 times consecutively[cite: 7].
* **`u` (Undo):** Undoes the last action[cite: 7].
* **`Ctrl + r` (Redo):** Redoes the last undone action[cite: 7].

### 3. Exiting Vim Safely
* **`:q!`:** Force quits Vim without saving any unsaved changes[cite: 7].
* **`:w`:** Saves (writes) the file changes without exiting.
* **`:wq` or `ZZ`:** Saves changes and exits the editor.

## Main Notes
* Because Vim is pre-installed on virtually all servers, knowing basic Vim navigation ensures you can edit remote configuration files on headless systems[cite: 7].
* Run `vimtutor` in your terminal to practice real-time navigation and line manipulation[cite: 7].

## My Key Learning
Understanding Vim's modal design—specifically switching between Normal, Insert, and Command modes—is fundamental for performing quick configuration fixes on Linux systems[cite: 7].