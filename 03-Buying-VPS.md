# Chapter 3 - Buying a VPS

## Objective

Choose and purchase a Virtual Private Server (VPS) that is suitable for hosting a modern React application today and can later support a backend, database, authentication, and other production services.

The goal is to avoid changing hosting providers as the project grows.

---

# What is a VPS?

A Virtual Private Server (VPS) is a virtual machine that runs continuously on a physical server inside a data center.

Unlike shared hosting, a VPS provides:

- Dedicated CPU resources
- Dedicated RAM
- Dedicated Storage
- Full administrator (root) access
- Freedom to install any software

For this guide, the VPS will host:

- React Application
- Nginx
- Node.js (future)
- PostgreSQL (future)
- Redis (future)
- SSL Certificates

---

# Recommended VPS Specifications

| Resource | Recommended |
|----------|-------------|
| CPU | 2 vCPU |
| RAM | 8 GB |
| Storage | 100 GB NVMe SSD |
| Operating System | Ubuntu Server 24.04 LTS |

This configuration is sufficient for:

- Static React Website
- Future Node.js Backend
- Database
- Admin Dashboard
- Booking System

---

# Why These Specifications?

### CPU

2 vCPUs provide enough processing power for:

- Building React applications
- Running Node.js
- Serving HTTP requests
- Database operations

---

### RAM

8 GB allows multiple services to run simultaneously.

Example:

| Service | Approximate RAM Usage |
|----------|----------------------:|
| Ubuntu | 700 MB |
| Nginx | 50 MB |
| Node.js | 300 MB |
| PostgreSQL | 400 MB |
| Redis | 150 MB |

Leaving plenty of memory for future growth.

---

### Storage

100 GB NVMe SSD provides enough space for:

- Source code
- Build files
- Logs
- Backups
- Database
- Uploaded files

---

# Operating System

Select:

```text
Ubuntu Server 24.04 LTS
```

Reasons:

- Long Term Support (LTS)
- Excellent documentation
- Large community support
- Compatible with modern Node.js tools

Do not select:

- Windows Server
- CentOS
- Debian (unless already familiar)
- AlmaLinux

---

# Server Location

Choose the data center closest to the majority of your users.

Example:

- India
- Singapore
- UAE

Lower latency results in faster page loading.

---

# Hostname

Choose a meaningful hostname.

Examples:

```text
web-01
```

```text
production-web
```

Avoid generic names such as:

```text
server123
```

---

# Login Method

If prompted, choose:

```text
Password Authentication
```

SSH Keys can be configured later after the initial setup.

---

# IPv4 Address

Ensure the VPS includes a public IPv4 address.

This IP address will later be connected to your domain.

---

# Root Password

Create a strong password.

Recommendations:

- Minimum 16 characters
- Uppercase letters
- Lowercase letters
- Numbers
- Symbols

Store the password securely using a password manager.

---

# Information to Save

After purchasing the VPS, record the following information:

| Item | Value |
|------|-------|
| Public IP Address | |
| Username | root |
| Password | |
| Operating System | Ubuntu 24.04 LTS |
| Data Center Location | |

This information will be required when connecting to the server.

---

# Verification Checklist

- [ ] VPS purchased.
- [ ] Ubuntu 24.04 LTS selected.
- [ ] Correct server location selected.
- [ ] Public IPv4 assigned.
- [ ] Root password saved securely.
- [ ] Public IP address recorded.

---

# Summary

In this chapter we:

- Selected the VPS specifications.
- Chose Ubuntu Server.
- Selected the server location.
- Configured administrator access.
- Recorded the server credentials.

The VPS is now ready for the initial server configuration.

➡ **Next Chapter:** `04-Initial-VPS-Setup.md`

---

# Commands Used

No commands were used in this chapter.