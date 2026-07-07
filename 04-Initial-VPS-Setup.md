# Chapter 4 - Initial VPS Setup

## Objective

Connect to the VPS for the first time, perform the initial Ubuntu setup, update the operating system, create a dedicated deployment user, and prepare the server for hosting applications.

At the end of this chapter, the server will be updated, secured, and ready for software installation.

---

# Prerequisites

Before continuing, ensure you have:

- Purchased a VPS
- Ubuntu Server 24.04 LTS installed
- Public IPv4 Address
- Root Username
- Root Password
- Internet Connection

---

# Step 1 - Open a Terminal

### Windows

Open one of the following:

- Windows Terminal (Recommended)
- PowerShell
- Command Prompt
- PuTTY

Windows Terminal is recommended because it supports SSH out of the box.

---

# Step 2 - Connect to the VPS

Run:

```bash
ssh root@YOUR_SERVER_IP
```

Example

```bash
ssh root@103.120.15.25
```

---

## Understanding the Command

| Part | Meaning |
|------|----------|
| ssh | Secure Shell program used to remotely access another computer |
| root | Administrator account on the server |
| @ | Connect as this user |
| YOUR_SERVER_IP | Public IP address of the VPS |

---

# Step 3 - Verify the Server Fingerprint

The first time you connect, Ubuntu displays something similar to:

```text
The authenticity of host '103.xxx.xxx.xxx' can't be established.

Are you sure you want to continue connecting (yes/no)?
```

Type

```text
yes
```

and press Enter.

This only appears the first time you connect.

---

# Step 4 - Enter the Password

After typing:

```text
yes
```

Ubuntu asks for the password.

```text
root@103.xxx.xxx.xxx's password:
```

Type the password provided by your VPS provider.

> **Note:** The cursor will not move while typing the password. This is normal.

Press Enter.

---

# Step 5 - Successful Login

If successful, you'll see something similar to:

```text
Welcome to Ubuntu 24.04 LTS

root@server:~#
```

The prompt indicates that you are now inside the VPS.

---

# Step 6 - Verify the Current User

Run:

```bash
whoami
```

Expected Output

```text
root
```

---

## Understanding the Command

`whoami`

Displays the currently logged-in user.

---

# Step 7 - Check the Current Directory

Run:

```bash
pwd
```

Expected Output

```text
/root
```

---

## Understanding the Command

`pwd`

Print Working Directory

Displays your current location in the Linux filesystem.

---

# Step 8 - List Files

Run:

```bash
ls
```

Expected Output

The folder may be empty or contain a few default files depending on your VPS provider.

---

## Understanding the Command

`ls`

Lists files and folders inside the current directory.

---

# Step 9 - Update Package Information

Run:

```bash
apt update
```

---

## Understanding the Command

| Command | Purpose |
|----------|----------|
| apt | Ubuntu package manager |
| update | Downloads the latest package information |

This command **does not install updates.**

It only refreshes the package index.

---

# Step 10 - Upgrade Installed Packages

Run:

```bash
apt upgrade -y
```

---

## Understanding the Command

| Part | Meaning |
|------|----------|
| apt | Package manager |
| upgrade | Installs available package updates |
| -y | Automatically answer "Yes" to prompts |

Depending on the VPS, this may take several minutes.

---

# Step 11 - Reboot if Required

Some updates require restarting the server.

Run:

```bash
reboot
```

The SSH connection will close.

Wait approximately one minute.

Reconnect:

```bash
ssh root@YOUR_SERVER_IP
```

---

# Step 12 - Verify Ubuntu Version

Run:

```bash
lsb_release -a
```

Expected Output

```text
Distributor ID: Ubuntu
Description: Ubuntu 24.04 LTS
```

---

# Step 13 - Verify Available Disk Space

Run:

```bash
df -h
```

This shows the available storage on the VPS.

Verify that the storage matches the VPS plan you purchased.

---

# Step 14 - Verify Available Memory

Run:

```bash
free -h
```

Verify that the RAM matches your VPS specifications.

---

# Step 15 - Verify CPU Information

Run:

```bash
lscpu
```

Confirm that the number of CPUs matches the purchased plan.

---

# Common Problems

## Permission Denied

```text
Permission denied
```

Possible Causes

- Incorrect password
- Incorrect username
- SSH disabled

---

## Connection Timed Out

Possible Causes

- Wrong IP address
- VPS not yet provisioned
- Firewall blocking SSH

---

## Host Identification Changed

This usually happens if:

- The VPS was reinstalled.
- The IP address now belongs to another server.

Remove the old SSH fingerprint before reconnecting.

---

# Verification Checklist

- [ ] Connected successfully using SSH.
- [ ] Logged in as root.
- [ ] Updated package lists.
- [ ] Installed system updates.
- [ ] Rebooted if required.
- [ ] Verified Ubuntu version.
- [ ] Verified storage.
- [ ] Verified RAM.
- [ ] Verified CPU.

---

# Summary

In this chapter we:

- Connected to the VPS using SSH.
- Logged in as the root user.
- Updated Ubuntu.
- Installed the latest system updates.
- Verified the server specifications.
- Prepared the VPS for software installation.

The server is now ready for installing development and hosting software.

➡ **Next Chapter:** `05-Installing-Required-Software.md`

---

# Commands Used

| Command | Purpose |
|----------|----------|
| `ssh` | Connect to the VPS |
| `whoami` | Show current user |
| `pwd` | Show current directory |
| `ls` | List files and folders |
| `apt update` | Refresh package list |
| `apt upgrade -y` | Install updates |
| `reboot` | Restart the server |
| `lsb_release -a` | Show Ubuntu version |
| `df -h` | Show disk usage |
| `free -h` | Show RAM usage |
| `lscpu` | Show CPU information |