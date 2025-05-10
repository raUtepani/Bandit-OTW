# Bandit Level 17 → Level 18


## Goal
> There are 2 files in the homedirectory: `passwords.old` and `passwords.new`. The password for the next level is in `passwords.new` and is the only line that has been changed between passwords.old and passwords.new

`NOTE:` if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19


## SSH
```bash
password : EReVavePLFHtFlFsjn3hyzMlvSuSAcRD
ssh bandit17@bandit.labs.overthewire.org -p 2220
```

# Solution
- The key idea is to compare two files — `passwords.old` and `passwords.new` — and identify the only changed line between them. That changed line in passwords.new contains the password for the next level.

- Use `diff` to compare the two files. The line that is present in passwords.new but not in passwords.old is the new password.
```bash
diff passwords.old passwords.new
```
Look for a line that starts with `> —` this indicates a line that is only in passwords.new, which is our target.

### Can also use grep
```bash
grep -v -f passwords.old passwords.new
```
- `-f passwords.old`: Uses passwords.old as a pattern file (each line is a pattern).
- `-v`: Inverts the match, showing lines in passwords.new that don’t match any line in passwords.old.


![level 17](/image/level17.png)