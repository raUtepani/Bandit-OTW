![screenshot of ls -al](/image/file_permission.png)


`-rw-r----- 1 bandit2 bandit1 33 Apr 10 14:23 -`
- **-**: It's a regular file (not a directory).

- **rw**-: The owner (bandit2) has read and write permissions.

- **r--**: The group (bandit1) has read-only access.

- **---**: Others (everyone else) have no access.

So: Only bandit2 can read and edit it, bandit1 (you) can only read it, and no one else can access it.


`drwxr-xr-x 2 root root 4096 Apr 10 14:23 .`
- **d**: This is a directory (specifically, the current one `.`).

- **rwx**: The owner (root) has full permissions (read/write/execute).

- **r-x**: The group (root) can read and enter, but not modify.

- **r-x**: Others also have read and execute access.


`drwxr-xr-x 70 root root 4096 Apr 10 14:24 ..`
- Same permissions and ownership as above.
- **..** is the parent directory.


`-rw-r--r-- 1 root root 220 Mar 31 2024 .bash_logout`
- **-**: Regular file.

- **rw**-: Owner (root) can read and write.

- **r--**: Group (root) can read only.

- **r--**: Others can read only.

✅ This file is a logout script that runs when a user logs out of the shell.


`-rw-r--r-- 1 root root 3771 Mar 31 2024 .bashrc`
- Same permissions as above.
✅ This is the shell configuration file that runs every time a new bash session is started.


`-rw-r--r-- 1 root root 807 Mar 31 2024 .profile`
Same permissions as above.
✅ This is a user profile script executed at login to set environment variables and preferences.

✅ Summary for Writeup
These are hidden configuration files (starting with .) used by the shell to set up the user environment. They are owned by root and readable by others, but only writable by root, ensuring normal users can’t alter system-wide behavior.


## 📌 What do the numbers 1 or 2 mean in ls -l output?
They represent the number of hard links to the file or directory.

`For files:`
- 1 means there is only one name (or path) pointing to this file on disk.
- If it were higher (like 2, 3, etc.), it would mean the file has multiple hard links (i.e., multiple names pointing to the same data on disk).

`For directories:`
- The count starts at 2:
- One for the directory itself.
- One for the . (current directory) reference inside it.
- It increases by 1 for each subdirectory, because each subdirectory contains a .. (parent) link back to it.

✅ Example:
```bash
-rw-r--r--  1 root root 220 Mar 31  2024 .bash_logout
1: Only one hard link to .bash_logout.
```

```bash
drwxr-xr-x  2 root root 4096 Apr 10 14:23 .
2: It’s a directory with no subdirectories, so just the . and .. links exist.
```
