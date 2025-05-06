# Bandit Level 1 → Level 2


## Goal
The password for the next level is stored in a file called `-` located in the home directory.


## Working with Dashed `-` Filenames in Linux
In Linux, a filename like `-` can be tricky because many commands treat `-` as a shortcut for standard input (stdin) or standard output (stdout).

Although `-` is not special to the filesystem, when it's the first character, the shell often assumes it’s an option `(like -h, -p or --help)`.

The usual syntax from cat `cat -` will not work as cat would consider `-` as an STDIN and wait for user INPUT(stdin) on the screen.So, when a file is actually named `-`, you must tell the command to treat it as a filename, not an option. You can tweak the cat syntax to check the content of (-). 
To read the contents of this file, use one of the following methods:

```bash
cat ./-
``` 
./- explicitly tells the shell: “this is a file in the current directory named -.”

```bash
cat -- -
```
`-- -` **--** ends option parsing, so everything after is treated as a file.

```bash
cat < -
```
`< -` Input redirection operator`<` — tells the shell to read input from a file `-` instead of the keyboard.


## SSH Details for Level 1
Here are the connection details:
- **Host:** `bandit.labs.overthewire.org` (This is the server you are connecting to)
- **Port:** `2220` (The port SSH is running on for this server)
- **Username:** `bandit1` (Your user account on the server)
- **Password:** `ZjLjTmM6FvvyRnrb2rfNWOZOTa6ip5If` (The password you need to log in)


## SSH Access

```bash
ssh bandit1@bandit.labs.overthewire.org -p 2220
```

![level 1](/image/level1.png)

- password is : `263JGJPfgU6LtdEvgfWU1XP5yac29mFx`
- use this password to login as a `bandit2` in the next level.


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


## links
- [Google Search for “dashed filename”](https://en.wikipedia.org/wiki/Secure_Shell)
- [Dashed filename in Linux](https://shorturl.at/g7RgK)
- [All about Dashed file from creation to deletion](https://shorturl.at/POt8u)
- [Advanced Bash-scripting Guide - Chapter 3 - Special Characters](https://www.wikihow.com/Use-SSH)


