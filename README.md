# Website Deployment Guide

A step-by-step guide for deploying a modern React application built with Vite on an Ubuntu VPS using Nginx.

The guide starts with deploying a static frontend and is designed so the same server can later be extended into a complete production environment with a backend, database, authentication, and other services.

---

## Objectives

By following this guide you will learn how to:

- Prepare a React project for production
- Host the application on an Ubuntu VPS
- Configure Nginx as a web server
- Connect a custom domain
- Secure the website with HTTPS
- Update the website safely after deployment
- Transition from a static frontend to a full-stack application

---

## Technology Stack

### Frontend

- React
- TypeScript
- Vite
- Tailwind CSS
- React Router

### Server

- Ubuntu Server
- Nginx
- Node.js
- Git

### Domain & SSL

- Any Domain Registrar (GoDaddy, Namecheap, etc.)
- Let's Encrypt SSL

---

## Deployment Roadmap

- [ ] Project Preparation
- [ ] Create Git Repository
- [ ] Purchase and Configure VPS
- [ ] Connect to VPS using SSH
- [ ] Install Required Software
- [ ] Deploy React Application
- [ ] Configure Nginx
- [ ] Connect Domain
- [ ] Install SSL Certificate
- [ ] Update Deployment Workflow
- [ ] Transition to Full-Stack Architecture

---

## Folder Structure

Static Website

```text
project/
│
└── client/
```

Future Full Stack

```text
project/
│
├── client/
└── server/
```

---

## Guide Structure

| Chapter | Topic |
|----------|-------|
| 01 | Project Preparation |
| 02 | Git Repository Setup |
| 03 | Buying a VPS |
| 04 | Initial Server Configuration |
| 05 | Deploying a React Application |
| 06 | Connecting a Domain |
| 07 | Installing SSL |
| 08 | Updating the Website |
| 09 | Migrating to a Full-Stack Application |

---

## Prerequisites

- Basic knowledge of Git
- Basic React knowledge
- A GitHub account
- A VPS
- A registered domain name
- SSH access to the server

---

This guide follows a practical approach. Every chapter documents the exact steps performed during deployment, including commands, explanations, verification steps, and common issues.