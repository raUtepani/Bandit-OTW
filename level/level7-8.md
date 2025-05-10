# Bandit Level 7 → Level 8


## Goal
The password for the next level is stored in the file `data.txt` next to the word millionth.
if we find the word millionth we will find the password.


## Login info
- **Username:** `bandit7`
- **Password:** `morbNTDkSW6jIlUc0ymOdMaLnOlFVAaj`


## SSH Access

```bash
ssh bandit7@bandit.labs.overthewire.org -p 2220
```


## Solution
```bash
grep millionth data.txt
```

![level 7](/image/level7.png)


- password is : `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`
- use this password to login as a `bandit8` in the next level.


## Commands may need to solve this level

- `grep`
The grep command in Linux is used to search for text patterns in files or output.

- `man` 
Displays the manual page for a command; helpful for learning how to use it (e.g., man grep).

- `uniq`
Filters out repeated lines in sorted input; often used with sort.

- `sort`
Sorts lines of text alphabetically or numerically.

- `strings`
Extracts readable ASCII text from binary files.