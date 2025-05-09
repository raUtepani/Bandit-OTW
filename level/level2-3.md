# Bandit Level 2 → Level 3


## Goal
The password for the next level is stored in a file called spaces in this filename located in the home directory.


## How to Tackle Filenames With Spaces in Linux
The one thing you'll notice that files in Linux usually do not contain spaces in their names.we use underscore instead of spaces in file and directory names.

It's not that you cannot use spaces in file names in Linux terminal. It's just that it creates additional pain and that's why you should avoid it wherever possible.

Why? Let me show that with examples. You know the generic syntax for Linux commands:
```bash
command [options] argument1 argument2
```
In here, the arguments are separated by spaces. If you try to use filenames with spaces directly, it will be treated as separate arguments rather than just one argument.

When i try to use `cat spaces in this filename` command, it doesn't understand that `spaces in this filename` is a single argument. It treats spaces,in,this and filename as different filenames.


## There are two ways to deal with spaces in filename:

1. Wrap the entire filename between quotes:
```
cat "spaces in this filename"
```

2. Escape every space using backslash key:
```
cat \spaces\ in\ this\ filename
```

## SSH Details for Level 1
Here are the connection details:
- **Host:** `bandit.labs.overthewire.org` (This is the server you are connecting to)
- **Port:** `2220` (The port SSH is running on for this server)
- **Username:** `bandit2` (Your user account on the server)
- **Password:** `263JGJPfgU6LtdEvgfWU1XP5yac29mFx` (The password you need to log in)


## SSH Access

```bash
ssh bandit2@bandit.labs.overthewire.org -p 2220
```

![level 2](/image/level2.png)

- password is : `MNk8KNH3Usiio41PRUEoDFPqfxLPlSmx`
- use this password to login as a `bandit3` in the next level.


## links
- [Google Search for “spaces in filename”](https://www.google.com/search?q=spaces+in+filename)
- [spaces in filename](https://linuxhandbook.com/filename-spaces-linux/)



