# **Bandit Level 31 → Level 32**

##  Goal

> There is a git repository at `ssh://bandit31-git@localhost/home/bandit31-git/repo` via the port 2220. The password for the user bandit31-git is the same as for the user bandit31.

> Clone the repository and find the password for the next level.



#  What is .gitignore?
A `.gitignore` file tells Git which files or directories to ignore — meaning Git won’t track changes to them, commit them, or show them as "untracked".

![level 31](/image/level31.png)

##  Login Info

```bash
ssh bandit31@bandit.labs.overthewire.org -p 2220
password: fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```


# Solution steps
### Create a temporary working directory `/temp`
```bash
mktemp -d
cd path_to _folder
```

### Clone the repo in that folder
```bash
git clone ssh://bandit31-git@localhost:2220/home/bandit31-git/repo
password : fb5S2xb7bRyFmAvQYQGEqsbhVyJqhnDy
```

![level 31](/image/level31II.png)

![level 31](/image/level31III.png)

1. The `README` states that we have to push a file to the repository. So first, we create the file. 
2. Now we can try to push the new file by first making a commit and then pushing it. However, this will not work because of the file `.gitignore` in the repo. 
3. This file lists `files/-types` that git will not push to the repository. In this case, exactly all files ending with `.txt`.

![level 31](/image/level31IV.png)