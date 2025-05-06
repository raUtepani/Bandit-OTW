# Bandit Level 3 → Level 4


## Goal
The password for the next level is stored in a `hidden file` in the `inhere directory`.


## How to read content of Hidden file
In Linux, files that begin with a dot (.) are considered hidden. They are not displayed by default when you use the ls command. To view hidden files, you must use the `-a` or `-al` flag.
Notice how its name begins with a .? This character is telling us that the file is hidden. This is common for all Unix-like operating systems: whenever a file is to be treated as hidden, we rename it by prepending a . character to its name.

We can directly use cat to the hidden file or use `./` which ensures the shell treats it as a filename in the current directory, not as a special pattern.
```bash
cat .hidden
```

```bash
cat ./.hidden
```


## SSH Details for Level 1
Here are the connection details:
- **Host:** `bandit.labs.overthewire.org` (This is the server you are connecting to)
- **Port:** `2220` (The port SSH is running on for this server)
- **Username:** `bandit3` (Your user account on the server)
- **Password:** `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx` (The password you need to log in)


## SSH Access

```bash
ssh bandit3@bandit.labs.overthewire.org -p 2220
```

![level 3](/image/level3.png)

- password is : `2WmrDFRmJIq3IPxneAaMGhap0pFhF3NJ`
- use this password to login as a `bandit4` in the next level.


## Commands Used
 
- `whoami`  
  Shows the current logged-in user (helpful to confirm which user you are).

- `pwd`  
  Prints the current working directory (shows where you are in the filesystem).

- `ls`  
  Lists files and directories in the current location.

- `cd`  
  The cd (change directory) command in Linux is used to navigate between different directories in the file system.

- `cat`  
  Displays the contents of the file.

- `file`  
  helps you identify file types (e.g., ASCII text, image, etc.).

- `find`  
  used to search for files and directories within a specified location.for locating files by name in directories.

- `du`  
  disk usage

- `ls -al`
  ls -al is a Linux command that lists all files and directories, including hidden ones, in a detailed format showing permissions, ownership, size, and modification time.

