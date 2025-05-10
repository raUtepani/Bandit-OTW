# Bandit Level 15 → Level 16


## Goal
The password for the next level can be retrieved by submitting the password of the current level to port 30001 on localhost using SSL/TLS encryption.


## ssh
```bash
password : 8xCjnmgoKbGLhHFAZlGE5Tmu4M2tKJQo
ssh bandit15@bandit.labs.overthewire.org -p 2220
```


## Solution
we already have password of bandit15. Unlike the previous level, this port requires encryption (SSL/TLS), so you can't just use `nc` — you’ll need something like `openssl s_client`.

```bash
openssl s_client -connect localhost:30001

```
You’ll see SSL handshake messages (like CONNECTED, certificate details, etc.). Once the connection is established and you see. It provides a read block to encrypt data where we submit our password to current level. It then sends back the password to bandit16.


![level 15](/image/level15.png)


## links
- [Secure Socket Layer/Transport Layer Security on Wikipedia](https://en.wikipedia.org/wiki/Transport_Layer_Security)
- [OpenSSL Cookbook - Testing with OpenSSL](https://www.feistyduck.com/library/openssl-cookbook/online/testing-with-openssl/index.html)
