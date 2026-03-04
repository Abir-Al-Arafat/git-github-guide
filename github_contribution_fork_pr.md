# GitHub Contribution Guide

This document outlines the workflow for contributing to this repository, specifically covering the process from forking to submitting a Pull Request (PR) for new features or API integrations.

## 1. Fork and Clone

Before making changes, ensure you have your own copy of the repository.

1. **Fork** the repository on GitHub to your own account.
2. **Clone** your fork locally:

```bash
git clone https://github.com/YOUR_USERNAME/repository-name.git
cd repository-name

```

3. **Add the Upstream Remote** (to stay synced with the original owner):

```bash
git remote add upstream https://github.com/ORIGINAL_OWNER/repository-name.git

```

## 2. Branching Strategy

Never work directly on the `main` or `master` branch. Always create a descriptive feature branch.

```bash
# Create and switch to a new branch
git checkout -b feature/api-integration

```

## 3. Development and Integration

Perform your API integration or code changes.

- Keep commits small and descriptive.
- Ensure all environment variables (API Keys, Secrets) are handled via `.env` files and **not** committed to Git.

```bash
git add .
git commit -m "feat: integrate external weather API and update types"

```

## 4. Staying Synced

To avoid merge conflicts, pull the latest changes from the original repository before pushing your work.

```bash
git checkout main
git pull upstream main
git checkout feature/api-integration
git merge main

```

## 5. Pushing to Your Fork

Upload your local branch to your GitHub account:

```bash
git push origin feature/api-integration

```

## 6. Submitting a Pull Request (PR)

Once the code is pushed, notify the original repository owner:

1. Navigate to the **original repository** on GitHub.
2. Click the **"Compare & pull request"** banner (usually appears automatically after a push).
3. **Review the Diff:** Ensure only the intended files are changed.
4. **Fill out the Template:**

- **Title:** Clear summary (e.g., `feat: Add Stripe API Integration`).
- **Description:** Explain _what_ was changed and _how_ to test it.

5. Click **"Create pull request"**.

---

## 7. Post-Submission

- **Code Review:** The maintainer may leave comments on specific lines.
- **Updating the PR:** If changes are requested, simply make the changes locally, commit, and push to the **same branch**. The PR updates automatically.
- **Cleanup:** Once the PR is merged, you can safely delete your local and remote feature branch.

```bash
git branch -d feature/api-integration
git push origin --delete feature/api-integration

```

---
