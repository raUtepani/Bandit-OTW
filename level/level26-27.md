# Bandit Level 26 → Level 27

## Level Goal  
> Good job getting a shell! Now hurry and grab the password for bandit27!

---
##  Login Info
Use the following to log into Bandit level 25:

```bash
ssh bandit26@bandit.labs.overthewire.org -p 2220
password: s0773xxkk0MXfdqOfPRVr9L3jJBUOgCZ
```
This is the same way to login as we did in previous level bandit 25.
Once logged in, check your current directory:
```bash
ls
```

```bash
ls -al
```

output:

```bash
-rwsr-x---  1 bandit27 bandit26 14884 Apr 10 14:23 bandit27-do
-rw-r-----  1 bandit26 bandit26   258 Apr 10 14:23 text.txt
```

```bash
file bandit27-do
bandit27-do: setuid ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, interpreter /lib/ld-linux.so.2, BuildID[sha1=35d353cf6d732f515a73f50ed205265fe1e68f 90, for GNU/Linux 3.2.0, not stripped
```


### Observations

- `bandit27-do` is a **setuid** binary owned by `bandit27` and executable by `bandit26`.
- This means we can run commands **as user `bandit27`** using this binary.

---
## Use the helper binary to read the password
```bash
./bandit27-do cat /etc/bandit_pass/bandit27
```

Output:

```
upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

![level 26](/image/level26.png)

![level 26](/image/level26II.png)