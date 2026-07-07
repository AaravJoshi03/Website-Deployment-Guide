# Chapter 1 - Project Preparation

## Objective

Before deploying a React application, ensure that the project is production-ready. A deployment should never begin until the application has been tested locally and can successfully generate a production build.

---

# Step 1 - Verify the Project Structure

A typical React + Vite project should look similar to this:

```text
project/
│
├── client/
│   ├── src/
│   ├── public/
│   ├── package.json
│   ├── package-lock.json
│   ├── vite.config.ts
│   ├── tsconfig.json
│   ├── .gitignore
│   └── ...
│
├── README.md
└── .gitignore
```

---

# Step 2 - Verify the `.gitignore`

Ensure the project ignores generated files and sensitive information.

Example:

```gitignore
node_modules/
dist/
.env
.env.*
.vscode/
```

### Why?

- `node_modules` can always be recreated using `npm install`.
- `dist` is generated every time the project is built.
- `.env` files often contain secrets that should never be committed to version control.

---

# Step 3 - Install Dependencies

Navigate to the frontend project.

```bash
cd client
```

Install all required packages.

```bash
npm install
```

This downloads every dependency listed inside `package.json`.

---

# Step 4 - Start the Development Server

Run:

```bash
npm run dev
```

Open the local URL shown in the terminal.

Verify that:

- Pages load correctly
- Images appear
- Icons render correctly
- Navigation works
- Animations work
- Browser console contains no errors

---

# Step 5 - Generate a Production Build

Run:

```bash
npm run build
```

If successful, Vite creates a new folder:

```text
dist/
```

This folder contains the optimized production version of the application.

---

# Step 6 - Test the Production Build

Run:

```bash
npm run preview
```

Open the preview URL.

This simulates how the application will behave after deployment.

Verify that:

- Every page loads correctly.
- Images load correctly.
- Routing works correctly.
- Styling matches the development build.
- Browser console contains no errors.

---

# Step 7 - Check for Local Development URLs

Search the project for:

```text
localhost
127.0.0.1
http://
```

If the application communicates with a backend, replace local URLs with environment variables before deployment.

For a purely static website, there should be no local backend URLs.

---

# Step 8 - Commit the Latest Changes

Save the current state of the project.

```bash
git add .
```

```bash
git commit -m "Prepare project for deployment"
```

```bash
git push
```

---

# Verification Checklist

- [ ] Project builds successfully.
- [ ] `npm run preview` works.
- [ ] No console errors.
- [ ] Images load correctly.
- [ ] Routing works correctly.
- [ ] `.gitignore` is configured correctly.
- [ ] Latest code has been pushed to GitHub.

---

# Summary

In this chapter we:

- Verified the project structure.
- Configured `.gitignore`.
- Installed all project dependencies.
- Tested the application in development mode.
- Generated a production build.
- Verified the production build using `npm run preview`.
- Checked for local development URLs.
- Committed and pushed the latest code to GitHub.

The project is now production-ready and prepared for deployment.

➡ **Next Chapter:** `02-Git-Repository-Setup.md`
