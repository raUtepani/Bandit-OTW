# Bandit Level 4 → Level 5


## Goal
The password for the next level is stored in the only human-readable file in the inhere directory. `Tip:` if your terminal is messed up, try the “reset” command.


## How to find file which stores in a human-readable format
use file command to check type of a file.
```bash
file ./*
```
It checks the file type of all files in the current directory, including those with names starting with a dash (-). The `./*` pattern ensures the shell treats every file as a regular filename, preventing errors caused by filenames that start with special characters. Then use `cat` to read content of that file.

```bash
cat file
```
OR use 
```bash
strings ./-file*
```
it will gives a human readable text only.


## SSH Details for Level 1
Here are the connection details:
- **Host:** `bandit.labs.overthewire.org` (This is the server you are connecting to)
- **Port:** `2220` (The port SSH is running on for this server)
- **Username:** `bandit4` (Your user account on the server)
- **Password:** `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ` (The password you need to log in)


## SSH Access

```bash
ssh bandit4@bandit.labs.overthewire.org -p 2220
```


![level 4](/image/level4.png)

![level 4](/image/level4.1.png)

- password is : `4oQYVPkxZOOEOO5pTW81FB8j8lxXGUQw`
- use this password to login as a `bandit5` in the next level.
