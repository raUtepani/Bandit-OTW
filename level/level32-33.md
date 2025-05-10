# **Bandit Level 32 → Level 33**

##  Goal

> After all this git stuff, it’s time for another escape. Good luck!


##  Login Info

```bash
ssh bandit32@bandit.labs.overthewire.org -p 2220
password: 3O9RfhqyAlVBEZpVb6LYStshZoqoSx5K
```

After ssh login it runs a diffirent shell `WELCOME TO THE UPPERCASE SHELL`. each and every command is transformed to a capital letter so  that command is not executing there.

```bash
>> ls
sh: 1: LS: Permission denied
>> 
```
![level 32](/image/level32.png)


Every Command we type seems to be made uppercase. The commands we have used so far however, are all lower-case and do not work. The one thing in Linux that is uppercase is variables. Specifically, the variable $0 has a reference to a shell. You can see this with `$0` on your machine. This lets us break out of the uppercase shell and we can use commands again.


# Why $0
![level 32](/image/level32II.png)

![level 32](/image/level32III.png)
