
# Bandit Level 25 → Level 26

##  Goal

> Log into the `bandit26` account from `bandit25`. However, `bandit26` doesn’t use a normal shell like Bash. You’ll need to find out what shell is used, understand how it works, and figure out how to escape it.

> **Note for Windows users:** If you're using PowerShell to connect via SSH, it may not work properly in this level. Use **Command Prompt** (`cmd.exe`) instead.

---

##  Login Info
Use the following to log into Bandit level 25:

```bash
ssh bandit25@bandit.labs.overthewire.org -p 2220
password: iCi86ttT4KSNe1armKiwbQNmB3YJP3q4
```

Once logged in, check your current directory:

```bash
ls
```
![level 25](/image/level25.png)

You’ll see a file named `bandit26.sshkey`. This is a private key to access `bandit26`.

---

##  First Attempt: Using the SSH Key

Let’s try using the private key to log in to `bandit26`:

```bash
ssh -i bandit26.sshkey bandit26@localhost
```
![level 25](/image/level25II.png)

You’ll see some text bandit26 (likely a banner), and then you’re immediately logged out. That’s strange — you didn’t even get a command prompt.

---

##  Investigating the Problem

Every Linux user account is assigned a **default shell** — like Bash or Zsh — which controls what happens when you log in. To see what shell `bandit26` uses, check the system’s user configuration file. The information, what shell is the default for a user, can be found at the end of the line for the user in the `/etc/passwd` file. The challenge mentions that the shell for bandit26 isn’t bash, so let’s see what it has instead.

```bash
cat /etc/passwd | grep bandit26
```

![level 25](/image/level25III.png)

You’ll see something like this:

```
bandit26:x:11026:11026::/home/bandit26:/usr/bin/showtext
```
- `bandit26` – The username. This is the login name of the user.
- `x` – This used to be the password, but now typically just an x indicating the actual password is stored in /etc/shadow (a more secure location).
- `11026` – The User ID (UID). A unique number that the system uses to identify the user.
- `11026` – The Group ID (GID). The user's primary group ID, also likely bandit26.
- `bandit level 26` – The user description or comment field (GECOS). Often used for the full name or other info.
- `/home/bandit26` – The home directory for this user.
- `/usr/bin/showtext` – The login shell or command run when this user logs in. Instead of a shell like `/bin/bash`, this user runs the `showtext` program upon login.


The last part (`/usr/bin/showtext`) is the shell. But this isn’t a typical shell — it’s a script or program.

---

##  Understanding `/usr/bin/showtext`

```bash
cat /usr/bin/showtext
```

![level 25](/image/level25IV.png)


```bash
#!/bin/sh

export TERM=linux

exec more ~/text.txt
exit 0
```

This script runs the `more` command to show the contents of a file, then exits. That’s why when you SSH into `bandit26`, it just shows a message and logs you out — it’s not a shell at all!

---

## Loophole in `more`

The `more` command is interactive — but **only if** `the text doesn’t fit on one screen.`

If the content fits within your terminal window, it will immediately show it and quit, which then triggers the `exit` in the script. But if the content doesn’t fit, `more` pauses and waits for your input — and that gives us an opportunity.

###  Solution:
1. **Resize your terminal window** to be very small — about 10 lines tall. This will force `more` to stop and wait for input when it runs.

![level 25](/image/level25V.png)

2. Now SSH again into `bandit26`:

   ```bash
   ssh -i bandit26.sshkey bandit26@localhost
   ```

3. If done correctly, `more` will pause and display a `:` prompt at the bottom. Press `v`.

   This launches the `vi` text editor (short for `vim`), which is often available in `more`.

![level 25](/image/level25VI.png)

![level 25](/image/level25VII.png)
---

##  Escaping to a Real Shell

Now that you’re in `vi`, you can spawn a real shell. In `vi`, type the following command and press Enter:

```bash
:set shell=/bin/bash
```

Then type:

```bash
:shell
```

Boom  — you're now in a real Bash shell as `bandit26`.

---

##  Get the Password for Level 26
 Read the password file:

```bash
cat /etc/bandit_pass/bandit26
```
![level 25](/image/level25VIII.png)

This will display the password for the next level.


## links
- [Youtube Video](https://youtu.be/gFh6iAGgzys?si=YN4Z-MOwi4In4Te3)
- [How to change shell in VIM](https://unix.stackexchange.com/questions/476468/change-the-shell-of-vim)
- [MOre on Wikipedia](https://en.wikipedia.org/wiki/More_(command))