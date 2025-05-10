# Bandit Level 10 → Level 11


## Goal
The password for the next level is stored in the file `data.txt`, which contains base64 encoded data


## Login info
- **Username:** `bandit10`
- **Password:** `FGUW5ilLVJrxX9kMYMmlN4MgbpfMiqey`


## SSH Access

```bash
ssh bandit10@bandit.labs.overthewire.org -p 2220
```


## Solution
```bash
base64 -d data.txt
```

- `base64` : Encodes and decodes data in base64 format.
- `-d` : Stands for decode. Use it to convert base64-encoded content back to its original form.


![level 10](/image/level10.png)


- password is : `dtR173fZKb0RRsDFSGsg2RWnpNVj3qRr`
- use this password to login as a `bandit11` in the next level.


## links
- [base64 on wikepedia](https://en.wikipedia.org/wiki/Base64)