# Bandit Level 18 → Level 19


## Goal
> The password for the next level is stored in a file readme in the home directory. Unfortunately, someone has modified .bashrc to log you out when you log in with SSH.

As mentioned in the Bandit Level 17 note:<br>
`NOTE:` if you have solved this level and see ‘Byebye!’ when trying to log into bandit18, this is related to the next level, bandit19


## SSH
```bash
password : x2gLTTjFwMOhQ8oWNbMN362QKxfRqGlO
ssh bandit18@bandit.labs.overthewire.org -p 2220
```

# Solution
To solve Bandit Level 18, you need to execute a command right when logging in, before the logout script (.`bashrc` or similar) kicks you out.

```bash
ssh bandit18@bandit.labs.overthewire.org -p 2220 cat readme
```

![level 18](/image/level18.png)