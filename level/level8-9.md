# Bandit Level 8 → Level 9


## Goal
The password for the next level is stored in the file `data.txt` and is the only line of text that occurs only once.


## Login info
- **Username:** `bandit8`
- **Password:** `dfwvzFQi4mU0wfNbFOe9RoWskMLg7eEc`


## SSH Access

```bash
ssh bandit8@bandit.labs.overthewire.org -p 2220
```


## Solution
```bash
sort data.txt | uniq -u
```
- `sort data.txt` — sorts the lines alphabetically so that duplicates are grouped together.
- `uniq -u` — filters and displays only unique lines (those that occur once).

![level 8](/image/level8.png)


- password is : `4CKMh1JI91bUIZZPXDqGanal4xvAg0JM`
- use this password to login as a `bandit9` in the next level.

------

## links
- [piping and redirection](https://ryanstutorials.net/linuxtutorial/piping.php)