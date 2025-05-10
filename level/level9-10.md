# Bandit Level 9 → Level 10


## Goal
The password for the next level is stored in the file data.txt in one of the few human-readable strings, preceded by several ‘=’ characters.


## Login info
- **Username:** `bandit9`
- **Password:** `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`


## SSH Access

```bash
ssh bandit9@bandit.labs.overthewire.org -p 2220
```


## Solution

Simple cat command gives random  data
```bash
cat data.txt
```
Then if we use string command we can see password for next level.
```bash
strings data.txt | grep ====
```
- `strings` : Extracts and prints human-readable text from binary or non-text files.
- `grep` : Searches for lines matching a specific pattern. grep '====' filters lines containing four or more equal signs.
- `| (Pipe)` : Passes the output of one command as input to another.


![level 9](/image/level9.png)


![level 9II](/image/level9II.png)

- password is : `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`
- use this password to login as a `bandit10` in the next level.