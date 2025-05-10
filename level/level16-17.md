# Bandit Level 16 → Level 17


## Goal
> The credentials for the next level can be retrieved by submitting the password of the current level to a port on localhost in the range 31000 to 32000. 
- First find out which of these ports have a server listening on them. 
- Then find out which of those speak SSL/TLS and which don’t. 
- There is only 1 server that will give the next credentials, the others will simply send back to you whatever you send to it.


## SSH
```bash
password : kSkvUpMQ7lBYyCM4GBPvCvT1BfWRy0Dx
ssh bandit16@bandit.labs.overthewire.org -p 2220
```


# Solution

### find out open ports and which of those speak SSL/TLS and which don’t.
```bash
nmap -A localhost -p 31000-32000
```
- `-A`: Enables aggressive scan options. This includes:
1. OS detection (-O)
2. Version detection (-sV)
3. Script scanning (-sC)
4. Traceroute (--traceroute)

![level 16](/image/level16.png)

This revealed several open ports, including both plain and SSL services. Among them, port 31790 stood out because:
- It uses SSL/TLS.
- It responds with: `"Wrong! Please enter the correct current password."`
This indicates that `port 31790` is the intended service for this level. It doesn’t echo input back, but instead expects the current level's password and returns the next level's credentials upon correct submission.


### Use the openssl s_client command to connect and send the Bandit16 password:
```bash
openssl s_client -connect localhost:31790 -quiet
```
![level 16II](/image/level16II.png)

Upon sending the current level's password to the correct SSL-enabled port, the server responds with an RSA private key. This private key serves as the authentication credential to log into the next level (Bandit17) via SSH.

- Now copy the RSA private key. Move to `/tmp` directory and create a directory using 
`mktemp -d`
- Now make a file with extension .key and paste the RSA key.
- Change the permission of file using chmod 700.

![level 16III](/image/level16III.png)


### login to bandit17
```bash
ssh -i level17.key bandit17@localhost -p 2220
```
![level 16IV](/image/level16IV.png)


## links
- [port scanner](https://en.wikipedia.org/wiki/Port_scanner)