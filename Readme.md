# Git-AAO: Git Collaboration Simulation

This repository is a practical exercise in using Git and GitHub to simulate real-world collaboration scenarios, including branching, pull requests, conflict resolution, and multi-user workflows.

---

## 🚀 Purpose

To learn and demonstrate:
- Working with multiple branches
- Simulating team collaboration (multiple users)
- Handling merge conflicts
- Creating and managing pull requests
- Cleaning up Git history (branches, commits)

---

## 👥 Simulated Contributors

- **Hema**: Worked on `mainscreen.html`
- **Dharani Kumar**: Developed `signup.html`, also edited `mainscreen.html` (to simulate conflict)

---

## 🔄 Workflow Summary

1. Initialized Git repo and pushed to GitHub
2. Created feature branches: `feature/signup`, `update/mainscreen`
3. Made and committed changes to different files
4. Created pull requests from both branches to `master`
5. Merged Hema’s PR first
6. Tried to merge Dharani’s → ⚠️ **Merge conflict**
7. Resolved conflict and completed the merge
8. Cleaned up local and remote branches

---

## 📁 Files Created

- `Readme.md`
- `story1.txt`
- `story2.txt`
- `signup.html`
- `mainscreen.html`

---

## 🌿 Branching Strategy

| Branch Name         | Description                         |
|---------------------|-------------------------------------|
| `feature/signup`    | Dharani’s signup form feature       |
| `update/mainscreen` | Hema’s updates to main screen UI    |
| `master`            | Main production branch              |

---

## 🔀 Pull Request Process

- Each user created their own branch and pushed changes
- Opened PRs targeting the `master` branch
- Merged one PR first
- Second PR caused a **conflict** due to overlapping changes in `mainscreen.html`
- Conflict resolved via Git CLI or GitHub editor

---

## 💻 Commands Used

```bash
# Initialize repo & push to GitHub
git init
git remote add origin git@github.com:ADK-the-Man/Git-AAO.git
git add .
git commit -m "Initial commit"
git push -u origin master

# Create and switch to new branches
git checkout -b feature/signup
git checkout -b update/mainscreen

# Add & commit changes
git add signup.html
git commit -m "Worked and updated the Signup feature"
git add mainscreen.html
git commit -m "Modified Mainscreen html files and made changes in it"

# Push branches to GitHub
git push origin feature/signup
git push origin update/mainscreen

# Merge PRs on GitHub
# (First Hema's -> then Dharani’s to trigger conflict)

# Delete local and remote branches
git branch -d feature/signup
git push origin --delete feature/signup
git branch -d update/mainscreen
git push origin --delete update/mainscreen

# Conflict resolution (example)
git checkout feature/signup
git pull origin master  # triggers conflict
# Edit conflicted file manually
git add mainscreen.html
git commit -m "Resolved conflict in mainscreen.html"
git push
