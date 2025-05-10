# Bandit Level 20 → Level 21


## Goal
> There is a setuid binary in the homedirectory that does the following: 
- it makes a connection to localhost on the port you specify as a commandline argument. 
- It then reads a line of text from the connection and compares it to the password in the previous level (bandit20). 
- If the password is correct, it will transmit the password for the next level (bandit21).

`NOTE:` Try connecting to your own network daemon to see if it works as you think


## ssh
```bash
password : 0qXahG8ZjOVMN9Ghs7iOWsCfZyXOUbYO
ssh bandit20@bandit.labs.overthewire.org -p 2220
```

# Solution
1. open two terminals in which in one terrminal run listener
```bash
nc -lvnp <port>
```

2. In another terminal run that binary file `suconnect` in same port as listener.
```bash
./suconnect <port>
```

3. send password of current level from listener. if it is correct it sends a password for next level.


![level 20](/image/level20.png)

![level 20II](/image/level20II.png)

## links
- [setuid on wiki](https://en.wikipedia.org/wiki/Setuid)