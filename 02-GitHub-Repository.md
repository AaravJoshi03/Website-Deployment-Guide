# Chapter 2 - Git Repository Setup

## Objective

Before deploying an application, the source code should be stored in a Git repository. The VPS will later clone this repository and use it as the source for every deployment and update.

This chapter ensures that the repository is correctly configured and ready for production deployments.

---

# Step 1 - Create a New GitHub Repository

Create a new repository on GitHub.

Example repository settings:

Repository Name

```text
project-name
```

Visibility

```text
Private
```

> **Recommendation:** Keep company projects private unless there is a reason to make them public.

Do not initialize the repository with:

- README
- .gitignore
- License

These files already exist locally.

---

# Step 2 - Initialize Git (If Required)

If Git has not already been initialized, navigate to the project root and run:

```bash
git init
```

Verify:

```bash
git status
```

Expected output:

```text
On branch main

No commits yet
```

If the project is already using Git, this step can be skipped.

---

# Step 3 - Stage All Files

```bash
git add .
```

Verify:

```bash
git status
```

All project files should appear under:

```text
Changes to be committed
```

---

# Step 4 - Create the Initial Commit

```bash
git commit -m "Initial project setup"
```

Verify:

```bash
git log --oneline
```

Example:

```text
8fa1a3b Initial project setup
```

---

# Step 5 - Rename the Default Branch

Use:

```bash
git branch -M main
```

Verify:

```bash
git branch
```

Expected output:

```text
* main
```

---

# Step 6 - Connect the Remote Repository

Copy the repository URL from GitHub.

Example:

```text
https://github.com/username/project-name.git
```

Add the remote:

```bash
git remote add origin https://github.com/username/project-name.git
```

Verify:

```bash
git remote -v
```

Expected output:

```text
origin https://github.com/username/project-name.git (fetch)

origin https://github.com/username/project-name.git (push)
```

---

# Step 7 - Push the Repository

```bash
git push -u origin main
```

The `-u` flag sets the upstream branch so future pushes only require:

```bash
git push
```

---

# Step 8 - Verify on GitHub

Open the repository.

Verify that it contains:

```text
client/
README.md
.gitignore
```

Verify that the following folders are NOT uploaded:

```text
node_modules/
dist/
```

---

# Best Practices

- Keep the repository private.
- Never commit `.env` files.
- Never commit `node_modules`.
- Never commit `dist`.
- Commit frequently with meaningful commit messages.
- Push changes regularly.

---

# Verification Checklist

- [ ] Repository created.
- [ ] Git initialized.
- [ ] Remote configured.
- [ ] Code pushed successfully.
- [ ] Repository visible on GitHub.
- [ ] `.env` files are ignored.
- [ ] `node_modules` is not tracked.
- [ ] `dist` is not tracked.

---

# Summary

In this chapter we:

- Created a GitHub repository.
- Connected the local project to GitHub.
- Created the initial commit.
- Pushed the source code.
- Verified the repository contents.

The Git repository is now ready to be used by the VPS during deployment.

➡ **Next Chapter:** `03-Buying-a-VPS.md`