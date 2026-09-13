# 08 - Fun Learning Quiz: Organizing Local Users and Groups

Test your active recall on the concepts introduced in Lesson 08.

---

### Questions

1. **User Databases:** Which file stores publicly readable local account information, and which file securely stores encrypted password hashes?
2. **Account Creation:** What command creates a new user named `alisson`, and what command sets her initial password?
3. **Modifying Shells:** How do you change a user's default login shell to `/bin/zsh`?
4. **Group Assignment:** What flag combination must be used with `usermod` to append a new group to a user without overwriting existing secondary groups?
5. **Account Locking:** How do you lock a user's account using `passwd`, and why is this preferred over immediate deletion in enterprise environments?
6. **Orphan File Risk:** What security issue occurs if you delete a user account with standard `userdel` (without `-r`) and later create a new user account?
7. **Finding Files by UID:** What command searches the root filesystem for files owned by UID `1001` while hiding permission error outputs?
8. **Administrative Access:** What system group in RHEL grants members `sudo` execution privileges?
9. **Authentication Methods:** How does administrative execution via `sudo -i` differ from `su -` regarding security auditing and password sharing?
10. **Scalability:** Why do enterprise environments utilize central authentication solutions like Red Hat IdM instead of managing local files in `/etc/passwd`?