# Bandit Level 6 → Level 7


## Goal
The password for the next level is stored somewhere on the server and has all of the following properties: **owned by user bandit7**, **owned by group bandit6**, **33 bytes in size**


## Login info

- **Username:** `bandit6`
- **Password:** `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`


## SSH Access

```bash
ssh bandit6@bandit.labs.overthewire.org -p 2220
```


## Command explain
```bash
find / -type f -user bandit7 -group bandit6 -size 33c 2>/dev/null
```
- / — search the whole file system
- -type f — look for regular files
- -user bandit7 — file must be owned by user bandit7
- -group bandit6 — file must belong to group bandit6
- -size 33c — file must be exactly 33 bytes (c means bytes)
- 2>/dev/null — suppresses permission-denied errors

![level 6](/image/level6.png)


- password is : `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`
- use this password to login as a `bandit7` in the next level.