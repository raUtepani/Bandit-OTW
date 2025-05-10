# Bandit Level 27 → Level 28

##  Goal

> There is a git repository at `ssh://bandit27-git@localhost/home/bandit27-git/repo` via the `port 2220`. The password for the user bandit27-git is the same as for the user bandit27.

> Clone the repository and find the password for the next level.

---

##  Login Info
Use the following to log into Bandit level 25:

```bash
ssh bandit27@bandit.labs.overthewire.org -p 2220
password: upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```

# what is Git?
[Git](https://git-scm.com/) is a version control system that lets developers track changes in files and collaborate on code. In simple terms, Git allows you to **clone** remote code repositories, **inspect** changes, and **access historical versions** of files.

Key Git concepts:
- `git init` : to create a new Git repository/project.
- `git push` : updates remote repository.
- `git pull` : get updates from remote repository.
- `git clone`: Creates a local copy of a remote repository.
- `.git`: A hidden directory containing all version history and metadata. The ‘.git’ directory contains all information that is required for version control. It contains information about commits, the remote repository address, a log and more.
- `README`: A file commonly found in repos, often containing instructions or useful information for the repo.

In this level, we are cloning a repository over SSH to read a file that contains the password for the next level.

---

# Solution steps
### step 1 : Create a temporary folder in `/temp`
```bash
mktemp -d
cd path_to _folder
```

### Clone the repo in that folder
```bash
git clone ssh://bandit27-git@localhost/home/bandit27-git/repo
password : upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```
This donot worked because Git tried to connect to port 22 (the default SSH port), while Bandit uses port 2220. You must explicitly specify the port when cloning the Git repository.

```bash
git clone ssh://bandit27-git@localhost:2220/home/bandit27-git/repo
password : upsNCc7vzaRDx6oZC6GiR6ERwe1MowGB
```


### Change directory and list the content of repo
```bash
cd repo
ls
```
There is a one README file 

```bash
cat README
```

![level 27](/image/level27.png)

# links 
[cloning problem](https://shorturl.at/fkRTH)