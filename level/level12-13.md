# Bandit Level 12 → Level 13


## Goal
The password for the next level is stored in the file data.txt, which is a hexdump of a file that has been repeatedly compressed. For this level it may be useful to create a directory under `/tmp` in which you can work. Use `mkdir` with a hard to guess directory name. Or better, use the command `mktemp -d`. Then copy the datafile using cp, and rename it using mv (read the manpages!)


## What is Hexdump?
A hexdump is a hexadecimal view of binary data. Tools like `xxd` can convert binary files to a readable hex format (called "dumping") and back again (called "reversing").

In this level, the password file has been dumped to hex and then compressed multiple times. We need to reverse the hex and then decompress step by step.


## What is Compression & Decompression?
Compression is the process of reducing the size of a file by encoding its contents more efficiently. It's commonly used to save space or prepare data for faster transfer.

Decompression is the reverse process — it restores the original file from its compressed version.
There are different types of compression formats you'll encounter in this level:
 --------------------------------------------------------------------------
| Format  | Tool to Decompress | Command                                   |
| ------- | ------------------ | ----------------------------------------- |
| `gzip`  | `gunzip`           | `gunzip file.gz` or `gzip -d file.gz`     |
| `bzip2` | `bunzip2`          | `bunzip2 file.bz2` or `bzip2 -d file.bz2` |
| `tar`   | `tar`              | `tar -xf file.tar`                        |


## Login Info
- **Username:** `bandit12`
- **Password:** `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`


## SSH Access
```bash
ssh bandit12@bandit.labs.overthewire.org -p 2220
```


# Solution
1. Create a Temporary Working Directory
```bash
mkdir /tmp/mydir123  # Replace 'mydir123' with any unique name
```
OR
```bash
mktemp -d
```

2. Copy data.txt from your current (home) directory to `/tmp` and change directory.
```bash
cp data.txt /tmp/tmp.9y7AZv0IFU
cd /tmp/tmp.9y7AZv0IFU
```

3. Reverse the hexdump
The file is a hex dump. Convert it back to binary using `xxd -r`.
```bash
xxd -r data.txt > first
```

4. Identify file type of a new file
```bash
file first
```
we get `first: gzip compressed data, was "data2.bin"`

5. Rename file `first` to gzip format
```bash
mv first first.gz
```

6. Decompress the gzip file
```bash
gunzip first.gz
```

7. After decompression check file type again.file is in bzip2 format.rename file to bizip2 format and decompress again.
```bash
mv first first.bz2
bunzip2 first.bz2
```

8. Same process is repeated until file says "ASCII text" (or something similar):

9. file is in tar format
```bash
file first
mv first first.tar
tar xf first.tar
```
`x` tells extract and `f` tells file.

Repeat same process of decompression untill password for next level is found.You will have to decompress the file until you get a file with `filetype ASCII text`.

![level 12](/image/level12.png)

![level 12](/image/level12II.png)

- password is : `FO5dwFsc0cbaIiH0h8J2eUks2vdTDwAn`
- use this password to login as a `bandit13` in the next level.


## Commands Used

- `cp`
It is used to copy a file. `cp <source> <destination>` copies files.

- `mv`
Used to move or rename a files. `mv <source> <destination>` 

- `mkdir` 
mkdir <path> can be used to create a new directory.

- `xxd` : 
Convert to/from hexdump format.


## links
- [Hexdump](https://en.wikipedia.org/wiki/ROT13)