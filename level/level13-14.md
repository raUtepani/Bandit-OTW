# Bandit Level 13 → Level 14


## Goal
> The password for the next level is stored in `/etc/bandit_pass/bandit14` and can only be read by user `bandit14`. For this level, you don’t get the next password, but you get a private SSH key that can be used to log into the next level. 

> Note: localhost is a hostname that refers to the machine you are working on.


## Login Info
- **Username:** `bandit13`
- **Password:** `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`


## SSH Access
```bash
ssh bandit13@bandit.labs.overthewire.org -p 2220
```


## Solution
we have  private ssh key for bandit14.
```bash
ssh -i sshkey.private bandit14@localhost -p 2220
```

- `-i sshkey.private`: specifies the identity file (private SSH key) to use for authentication.
- `bandit14@localhost`: the username (bandit14) and host (localhost) you want to connect to.


```bash
cat /etc/bandit_pass/bandit14
```

- password is : `MU4VWeTyJk8ROof1qqmcBPaLh7lDCPvS`
- use this password to login as a `bandit14` in the next level.

## links
- [Openssh](https://help.ubuntu.com/community/SSH/OpenSSH/Keys)