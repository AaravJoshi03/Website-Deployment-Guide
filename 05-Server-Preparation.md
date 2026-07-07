# Chapter 5 - Server Preparation

## Objective

Prepare the Ubuntu VPS for production use by creating a dedicated deployment user, configuring user permissions, creating a project workspace, and enabling the firewall.

From this point onward, all application deployment will be performed using the deployment user instead of the root account.

---

# Why Not Use the Root User?

The `root` user has unrestricted access to the operating system.

While this is useful for initial server setup, using the root account for everyday development and deployment increases the risk of accidental system changes.

Instead, a dedicated deployment user should be used for:

- Cloning repositories
- Building applications
- Updating projects
- Running deployment scripts

The root account should only be used for server administration tasks.

---

# Step 1 - Create a Deployment User

Run:

```bash
adduser deploy
```

Ubuntu will ask for:

- Password
- Full Name (Optional)
- Room Number (Optional)
- Work Phone (Optional)
- Home Phone (Optional)
- Other Information (Optional)

Only the password is required.

For the remaining fields, simply press **Enter**.

---

# Step 2 - Add the User to the Sudo Group

Run:

```bash
usermod -aG sudo deploy
```

---

## Understanding the Command

| Part | Meaning |
|------|----------|
| usermod | Modify an existing user |
| -a | Append without removing existing groups |
| -G | Specify group |
| sudo | Administrative group |
| deploy | Username |

---

# Step 3 - Verify the User

Run:

```bash
id deploy
```

Expected output should include:

```text
groups=... sudo
```

This confirms the user has administrator privileges.

---

# Step 4 - Switch to the Deployment User

Run:

```bash
su - deploy
```

Verify:

```bash
whoami
```

Expected output:

```text
deploy
```

---

# Step 5 - Create a Projects Directory

Run:

```bash
mkdir -p ~/projects
```

Verify:

```bash
ls
```

Expected output:

```text
projects
```

This directory will contain all application source code.

---

# Step 6 - Create a Scripts Directory

Run:

```bash
mkdir ~/scripts
```

This folder will later contain deployment scripts.

---

# Step 7 - Create a Backups Directory

Run:

```bash
mkdir ~/backups
```

This folder can be used to store:

- Database backups
- Previous deployments
- Configuration backups

---

# Step 8 - Verify the Folder Structure

Run:

```bash
tree ~
```

If the `tree` command is not installed:

```bash
sudo apt install tree -y
```

Run again:

```bash
tree ~
```

Expected output:

```text
/home/deploy
├── backups
├── projects
└── scripts
```

---

# Step 9 - Configure the Firewall

Ubuntu includes UFW (Uncomplicated Firewall).

Check its status:

```bash
sudo ufw status
```

If inactive, allow SSH:

```bash
sudo ufw allow OpenSSH
```

Enable the firewall:

```bash
sudo ufw enable
```

Verify:

```bash
sudo ufw status
```

Expected output:

```text
Status: active
```

---

# Why Allow SSH First?

Never enable the firewall before allowing SSH.

Otherwise, you may block your own access to the server.

Always:

```text
Allow SSH

↓

Enable Firewall
```

---

# Step 10 - Verify Home Directory

Run:

```bash
pwd
```

Expected output:

```text
/home/deploy
```

---

# Verification Checklist

- [ ] Deployment user created.
- [ ] User added to sudo group.
- [ ] Logged in as deployment user.
- [ ] Projects directory created.
- [ ] Scripts directory created.
- [ ] Backups directory created.
- [ ] Firewall enabled.
- [ ] SSH allowed through the firewall.

---

# Server State After This Chapter

```text
Ubuntu Server
│
├── Updated
├── Deployment User
├── Firewall
├── Projects Folder
├── Scripts Folder
└── Backups Folder

Git            ❌
Node.js        ❌
Nginx          ❌
Website        ❌
Domain         ❌
SSL            ❌
```

---

# Summary

In this chapter we:

- Created a dedicated deployment user.
- Granted administrative privileges.
- Created the project workspace.
- Prepared directories for scripts and backups.
- Enabled the firewall while keeping SSH accessible.

The server is now ready for installing the software required to deploy applications.

➡ **Next Chapter:** `06-Installing-Git.md`

---

# Commands Used

| Command | Purpose |
|----------|----------|
| `adduser` | Create a new user |
| `usermod` | Modify a user's groups |
| `id` | Display user and group information |
| `su -` | Switch to another user |
| `mkdir` | Create directories |
| `tree` | Display directory structure |
| `ufw status` | Check firewall status |
| `ufw allow OpenSSH` | Allow SSH connections |
| `ufw enable` | Enable the firewall |
| `pwd` | Display current directory |