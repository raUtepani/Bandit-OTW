# **Bandit Level 29 → Level 30**

##  Goal

> There is a git repository at `ssh://bandit29-git@localhost/home/bandit29-git/repo` via the port 2220. The password for the user bandit29-git is the same as for the user bandit29.

> Clone the repository and find the password for the next level.

---

##  Login Info
Use the following to log into Bandit level 29:

```bash
ssh bandit29@bandit.labs.overthewire.org -p 2220
password: 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```
You will be prompted for the password for `bandit29-git`. Use the same password as the one for `bandit29`.


# Solution steps
### Create a temporary working directory `/temp`
```bash
mktemp -d
cd path_to _folder
```


### Clone the repo in that folder
```bash
git clone ssh://bandit29-git@localhost:2220/home/bandit29-git/repo
password : 4pT1t5DENaYuqnqvadYs1oE4QLCdjmJ7
```
You will be prompted for the password for `bandit29-git`. Use the same password as the one for `bandit29`.


###  Check Initial Repository Contents
```bash
ls
cd repo
cat README.md
```
This file contains some dummy credentials:

It says:
```
- username: bandit29
- password: <no passwords in production!>
```

![level 29](/image/level29.png)



# **Inspect commit history:**
```bash
git log
```
![level 29II](/image/level29II.png)

![level 29III](/image/level29III.png)

This reveals multiple commits modifying the README.md, including changes to the username. still no password for next level. let's check branches


# **Check All Remote Branches**
```bash
git branch -a
```
![level 29](/image/level29IV.png)


# Switch to the dev Branch
```bash
git checkout dev
```
List the contents inside this branch 

![level 29](/image/level29V.png)

Here we go we got the password.

Also this password can be gained from the latest commit in devbranch
![level 29](/image/level29VI.png)


nothing in sploits-dev branch 




