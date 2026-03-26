# Repository Setup

## Goal

Prepare this framework as a reusable GitHub repository before starting the first project.

## Local Setup

1. Initialize git in the repository root
2. Review and customize `README.md`
3. Review the included `LICENSE` and replace it if needed
4. Review `.github/` templates and workflows
5. Commit the framework baseline

## Suggested Commands

```powershell
git init
git add .
git commit -m "Initial framework scaffold"
git branch -M main
```

## GitHub Setup

1. Create a new GitHub repository
2. Add the remote
3. Push the `main` branch

```powershell
git remote add origin <your-repo-url>
git push -u origin main
```

## Before Reuse

- Copy this framework into a new working repository or use it as a template repository
- Run the bootstrap flow before any domain work starts
- Replace sample files with live project files as decisions become real

## Decisions Still Needed

- Final repository name
- Whether GitHub Actions should run by default or remain sample-only
