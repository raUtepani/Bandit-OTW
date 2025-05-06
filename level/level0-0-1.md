# Bandit Level 0 → Level 1


## Goal
Log into the game using SSH (Secure Shell), which is a protocol for securely accessing remote computers. The password for the next level is stored in a file called `readme` located in the home directory.Use this password to log into `bandit1` using SSH.


## What is SSH?
SSH allows you to connect to remote systems over the internet securely. It’s commonly used for accessing servers, transferring files, and running commands remotely.


## SSH Details for Level 0
To connect to the Bandit server, you need to use SSH. Here are the connection details:
- **Host:** `bandit.labs.overthewire.org` (This is the server you are connecting to)
- **Port:** `2220` (The port SSH is running on for this server)
- **Username:** `bandit0` (Your user account on the server)
- **Password:** `bandit0` (The password you need to log in)


## Solution
Using the terminal or shell, run the following SSH command to connect to the Bandit server:

```bash
ssh bandit0@bandit.labs.overthewire.org -p 2220
```

![level 1](/image/level01.png)

password is : `ZjLjTmM6FvvyRnrb2rfNWOZOT*******`.
- use this password to login as a `bandit1` in the next level.


## Commands Used

- `whoami`  
  Shows the current logged-in user (helpful to confirm which user you are).

- `pwd`  
  Prints the current working directory (shows where you are in the filesystem).

- `ls`  
  Lists files and directories in the current location.

- `cat`  
  Displays the contents of the file.

- `file`  
  helps you identify file types (e.g., ASCII text, image, etc.).

- `find`  
  used to search for files and directories within a specified location.for locating files by name in directories.

- `du`  
  disk usage


## links
- [secure Shell(SSH) on wikipedia](https://en.wikipedia.org/wiki/Secure_Shell)
- [How to use SSH on wikiHow](https://www.wikihow.com/Use-SSH)