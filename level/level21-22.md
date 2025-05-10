# Bandit Level 21 → Level 22


## Goal
> A program is running automatically at regular intervals from cron, the time-based job scheduler. Look in `/etc/cron.d/` for the configuration and see what command is being executed.


## ssh
```bash
password : EeoULMCra2q0dSkYj561DX7s1CpBuOBt
ssh bandit21@bandit.labs.overthewire.org -p 2220
```


## What is cron
Cron is a time-based job scheduler in Unix-like systems. It automatically runs scripts or commands at scheduled times or intervals (e.g., every minute, every hour, once a day).


## How cron works
Jobs are defined in special files called crontabs (short for "cron table").
- Each line in a crontab file specifies:
- When the job should run (minute, hour, day of month, etc.)
- What command or script to run
- Who the job runs as (in /etc/cron.d jobs)


# Solution

![level 21](/image/level21.png)

- `@reboot`: This special syntax means run the command once when the system starts (reboots).
- `bandit22`: Run the command as the bandit22 user.
- `/usr/bin/cronjob_bandit22.sh`: This is the script to run.
- `&> /dev/null`: Redirect both stdout and stderr (all output) to /dev/null, effectively discarding it.<br>
📌 In simple terms:
When the system reboots, run the script `/usr/bin/cronjob_bandit22.sh` as bandit22, and throw away any output.


![level 21II](/image/level21II.png)
- `* * * * *`: This cron expression means every minute.
- `bandit22`: Run as the bandit22 user.
- `/usr/bin/cronjob_bandit22.sh`: The script to run.
- `&>` /dev/null: Discard all output.
<br>
In simple terms: Run the script `/usr/bin/cronjob_bandit22.sh` every minute as bandit22, and don't show any output.

<br>
- `chmod 644 /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`<br>
This sets the file permissions to read/write for owner, read-only for group and others.
In other words: anyone (including you) can read the file at /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv.

- `cat /etc/bandit_pass/bandit22 > /tmp/t7O6lds9S0RqQh9aMcz6ShpAoZKF7fgv`<br>
This copies the password for bandit22 into the file in `/tmp`.


# Commands You May Need
1. cron <br> <br>
**What it is**: The daemon that runs scheduled tasks (cron jobs).<br>
**Relevance**: You don’t run this directly, but it's the service that executes the scheduled jobs found in `/etc/cron.d`.
<br> <br>
2. crontab<br>
**What it is**: A command to view or edit a user's cron jobs. Crontab, which is short for cron table, is a file containing the schedule of various cron entries that should be run at specified times. The crontab file contains simple instructions for the daemon that mean "run this command at this time on this date." These instructions specify which command will be executed, on which date and at what time. The file location varies depending on the OS.

Usage:
```bash
crontab -l       # List your current user's cron jobs
crontab -e       # Edit your current user's cron jobs
```

