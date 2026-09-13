# 06 - Fun Learning Answers: Basic File Management

Use these answers to check your responses from `06-FunLearningQuestions.md`.

---

### Answers

1. **Listing Details:**
   * `ls -lha`[cite: 6].

2. **Hidden File Convention:**
   * Their filenames begin with a leading period/dot (`.`)[cite: 6].

3. **Directory Creation:**
   * The `-p` flag creates nested parent directories if they do not exist and prevents the command from returning an error if the directory already exists[cite: 6].

4. **Verbose Feedback:**
   * The `-v` flag prints an explicit message to stdout for each directory created (e.g., `mkdir: created directory 'folder'`)[cite: 6].

5. **Creating Files:**
   * `touch <filename>`[cite: 6].

6. **Renaming vs. Moving:**
   * If the target destination is a directory path, `mv` moves the file into that folder[cite: 6]. If the target is a new filename in the current path, `mv` renames the file[cite: 6].

7. **Directory Removal:**
   * The recursive `-r` (or `-R`) flag[cite: 6].

8. **Safety Safeguards:**
   * The `-i` (interactive) flag forces `rm` to ask for user confirmation (`y/n`) before deleting each file or entering subdirectories[cite: 6].