The chmod command in Unix/Linux is used to `change the permissions of files or directories`. Permissions define who can read, write, or execute a file. There are two main ways to use chmod: 
- symbolic mode 
- numeric (octal) mode.

# 🔐 Linux File Permissions Basics
1. Each file or directory has three types of users:
- `User (u)` – the file owner
- `Group (g)` – users in the file’s group
- `Others (o)` – all other users

2. And three types of permissions:
- `r` = read
- `w` = write
- `x` = execute

![Numeric mode](/image/chmod1.png)

![Numeric mode](/image/chmod2.png)

![Symbolic mode](/image/symbolic.png)

```bash
chmod +x execute.sh # adds execute for all 
```
