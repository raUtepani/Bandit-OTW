# Bandit Level 5 → Level 6


## Goal
The password for the next level is stored in a file somewhere under the inhere directory and has all of the following properties: **human-readable**, **1033 bytes in size**,**not executable**


## Login INFO
- **Username:** `bandit5`
- **Password:** `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`


## SSH Access

```bash
ssh bandit5@bandit.labs.overthewire.org -p 2220
```


## command explanation
```bash
find . -type f -size 1033c ! -executable
```
- Look in the current directory (.)
- Find files (-type f)
- That are exactly 1033 bytes (-size 1033c, where c means bytes)

```bash
du -a -b ./maybehere* | grep 1033
```
- du = disk usage
- -a = list all files, not just directories
- -b = show size in bytes instead of blocks (this is key!)
- ./maybewhere* = searches files inside directories starting with maybewhere
- grep 1033 = filters the output to only show files that are exactly 1033 bytes

![level 5](/image/level5.png)

![level 5](/image/level5II.png)

- password is : `HWasnPhtq9AVKe0dmk45nxy20cvUa6EG`
- use this password to login as a `bandit6` in the next level.