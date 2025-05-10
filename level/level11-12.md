# Bandit Level 11 → Level 12


## Goal
The password for the next level is stored in the file `data.txt`, where all lowercase (a-z) and uppercase (A-Z) letters have been `rotated by 13 positions`.


# What is ROT13

- ROT13 is a simple letter substitution cipher that replaces a letter with the 13th letter after it in the Latin alphabet.An early entry on the Timeline of cryptography.
- ROT13 can be referred by "Rotate13", "rotate by 13 places", hyphenated "ROT-13".
- The data.txt file contains text which is encrypted using rot13 algorithm. To decrypt ROT13 encryption we translate the letters 13 position.
- `A -> M, a -> m, n->a, N->A` 
- Using tr command to translate we obtain the password. The Linux tr command, which stands for ’translate’, allows replacing characters with others. The base command syntax looks like the following `tr <old_chars> <new_chars>.`


## Login Info
- **Username:** `bandit11`
- **Password:** `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`


## SSH Access

```bash
ssh bandit11@bandit.labs.overthewire.org -p 2220
```


## Solution
```bash
cat data.txt
```
use cyberchief online to decypt ROT13 encrypted text.

OR
```bash
cat data.txt | tr 'A-Za-z' 'N-ZA-Mn-za-m'
```
- `cat` : Reads and prints the content of a file.
- `tr (translate)` : Translates characters from one set to another.
- `'A-Za-z' 'N-ZA-Mn-za-m'` : This defines the ROT13 transformation:
- `'A-Z' → 'N-ZA-M'` : rotates uppercase letters
- `'a-z' → 'n-za-m'` : rotates lowercase letters

![level 11](/image/level11.png)


- password is : `7x16WNeHIi5YkIhWsfFIqoognUTyj9Q4`
- use this password to login as a `bandit12` in the next level.


## links
- [Rot-13](https://en.wikipedia.org/wiki/ROT13)