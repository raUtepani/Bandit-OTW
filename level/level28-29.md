# Bandit Level 28 → Level 29

##  Goal

> There is a git repository at `ssh://bandit28-git@localhost/home/bandit28-git/repo` via the port 2220. The password for the user bandit28-git is the same as for the user bandit28.

> Clone the repository and find the password for the next level.

---

##  Login Info
Use the following to log into Bandit level 25:

```bash
ssh bandit28@bandit.labs.overthewire.org -p 2220
password: Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```
You will be prompted for the password for `bandit28-git`. Use the same password as the one for `bandit28`.


# Solution steps
### Create a temporary folder in `/temp`
```bash
mktemp -d
cd path_to _folder
```


### Clone the repo in that folder
```bash
git clone ssh://bandit28-git@localhost:2220/home/bandit28-git/repo
password : Yz9IpL0sBcCeuG7m9uQFt8ZNpS4HZRcN
```


### Check Initial Repository Contents
   ```bash
   cd repo
   cat README.md
   ```
   It says:
   ```
   - username: bandit29
   - password: xxxxxxxxxx
   ```
   The password is hidden in the current version.


![level 28](/image/level28.png)



# **Inspect commit history:**
we can check the past logs of the file using git log command.
```bash
git log
```
Three commits appear:
- Latest: “fix info leak”
- Second: “add missing data”
- First: “initial commit of README.md”

### **Check previous version where password was first added:**

![level 28](/image/level28II.png)
<br>
1. Check Initial commit

![level 28](/image/level28III.png)

2. Check second commit

![level 28](/image/level28IV.png)

This commit replaces `<TBD>` with the actual password. Reading content of README.md we can see the password which was removed in future commit.

![level 28](/image/level28V.png)