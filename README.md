# GIT / Github Docs

## Git

- Git is a distributed version control system (DVCS) that is widely used for tracking changes in source code during software development. It allows multiple developers to collaborate on a project, keeping track of their changes and managing different versions of the code.
- Git was created by Linus Torvalds in 2005 to manage the development of the Linux kernel.

## Github

- GitHub is a web-based platform that provides hosting for software development and version control using Git. It offers a range of collaborative features for developers, making it easier to work together on projects. GitHub is widely used for hosting and sharing code, managing projects, and facilitating collaboration among developers.

## Why is version control important

1. **History and Audit Trail:**

   - Version control systems maintain a complete history of changes, providing an audit trail for debugging and understanding the evolution of the code.

2. **Collaboration:**

   - Enables multiple developers to work on the same project concurrently, facilitating collaboration without interference.

3. **Branching and Parallel Development:**

   - Allows the creation of branches for independent development, supporting parallel work on features or bug fixes that can later be merged.

4. **Code Stability:**
   - Permits reverting to a stable state if new changes introduce issues, helping to maintain the stability of the codebase.

# Git Workflow for Developers

## 1. Pull Latest Updates

Before starting any development work, it's essential to ensure you have the latest updates from the repository. Use the following commands:

```bash
git pull origin main
```

This fetches the latest changes from the main branch of the remote repository and updates your local working copy.

## 2. Create a Feature Branch

To isolate your work and avoid directly modifying the main branch, create a new branch for your feature. Replace "feature-branch" with a descriptive name for your feature:

```bash
git checkout -b feature-branch #create and switch to branch
```

This command creates and switches to a new branch named "feature-branch."

or you can use this syntax

```bash
git branch feature-branch #create branch
git checkout feature-branch # switch to branch
```

## 3. Staging and Committing Changes

Make your changes to the code and stage them for commit. Here's a basic sequence:

```bash
# Stage all changes
git add .
# or
git add <file_path>
# Commit changes with a meaningful message
git commit -m "Implement new feature"
```

Repeat the staging and committing process as needed for your changes.

## 4. Push Feature Branch

Once your changes are committed locally, push the feature branch to the remote repository:

```bash
git push origin feature-branch # Origin Refers to the remote repository
```

## 5. Summary

Following these steps ensures you're working with the latest code, isolating your changes, and maintaining a clean and organized version history in the repository.



