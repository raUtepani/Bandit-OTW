# Bandit Level 19 → Level 20


## Goal
> To gain access to the next level, you should use the `setuid binary` in the home directory. Execute it without arguments to find out how to use it. The password for this level can be found in the usual place `(/etc/bandit_pass)`, after you have used the setuid binary.


## SSH
```bash
password : cGWpMaKXVwDUNgPAVJbWYuGHVn9zl3j8
ssh bandit19@bandit.labs.overthewire.org -p 2220
```

# Solution

1. when we check file permission of file 
```bash
-rwsr-x--- 1 bandit20 bandit19 12345 May 6 00:00 bandit20-do
```
- `s` in `rws` = setuid bit is set.
- It runs with `bandit20`'s permissions when executed by `bandit19`.

2. Run the binary without arguments to see usage:
```bash
./bandit20-do
```

3. Use it to read the password file of bandit20:
```bash
/bandit20-do cat /etc/bandit_pass/bandit20
```

![level 19](/image/level19.png)


## links
- [setuid on wiki](https://en.wikipedia.org/wiki/Setuid)