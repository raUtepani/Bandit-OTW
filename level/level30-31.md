# **Bandit Level 30 → Level 31**

##  Goal

> There is a git repository at `ssh://bandit30-git@localhost/home/bandit30-git/repo` via the port 2220. The password for the user bandit30-git is the same as for the user bandit30.

> Clone the repository and find the password for the next level.

---

##  Login Info

```bash
ssh bandit30@bandit.labs.overthewire.org -p 2220
password: qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```


# Git Tag
git tag is a Git command used to mark specific points in a repository’s history, typically used to label releases or important commits — like "v1.0", "stable".

![level 30](/image/level30.png)


# Solution steps
### Create a temporary working directory `/temp`
```bash
mktemp -d
cd path_to _folder
```

### Clone the repo in that folder
```bash
git clone ssh://bandit30-git@localhost:2220/home/bandit30-git/repo
password : qp30ex3VLz5MDG1n91YowTv4Q8l7CDZL
```


![level 30](/image/level30II.png)

![level 30](/image/level30III.png)