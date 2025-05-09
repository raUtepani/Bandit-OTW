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
 
- `find`  
  used to search for files and directories within a specified location.for locating files by name in directories.

- `du`  
  disk usage
