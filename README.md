# Table of Contents

- [GIT / Github](#git--github-docs)
  1.  [Git](#git)
  2.  [Github](#github)
- [Why is version control important](#why-is-version-control-important)
- [Git Workflow for Developers](#git-workflow-for-developers)
  1. [Pull Latest Updates](#1-pull-latest-updates)
  2. [Create a Feature Branch](#2-create-a-feature-branch)
  3. [Staging and Committing Changes](#3-staging-and-committing-changes)
  4. [Push Feature Branch](#4-push-feature-branch)
  5. [Post Feature Branch Push](#5-post-feature-branch-push)
  6. [Delete Local Branch](#6-delete-local-branch)

- [Resetting in Git: Strategies for Commit, Staging.](#resetting-in-git-strategies-for-commit-staging)

# GIT / Github

## Git

- Git is a distributed version control system (DVCS) that is widely used for tracking changes in source code during software development. It allows multiple developers to collaborate on a project, keeping track of their changes and managing different versions of the code.
- Git was created by Linus Torvalds in 2005 to manage the development of the Linux kernel.

## Github

- GitHub is a web-based platform that provides hosting for software development and version control using Git. It offers a range of collaborative features for developers, making it easier to work together on projects. GitHub is widely used for hosting and sharing code, managing projects, and facilitating collaboration among developers.

# Why is version control important

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

## 5. Post Feature Branch Push

- **After pushing, GitHub will provide a link to create a pull request.**

1. Navigate to "Pull Requests" on GitHub:
   Go to your repository on GitHub and click on the "Pull Requests" tab.

2. Click on the "New Pull Request" button.

3. Select Branches:

   Choose the main branch as the base branch.
   Select your feature branch as the compare branch.

4. Add Details:
   Provide a brief title and description summarizing your changes.

5. Assign Reviewer:
   Assign a reviewer responsible for approving changes.

6. Create Pull Request:
   Click the "Create Pull Request" button to open the pull request for review.

7. **Wait for Merging:**

   The pull request enters a review phase.
   The assigned reviewer inspects changes, provides feedback, and approves for merging.

8. **Make Adjustments**:
   Be responsive to feedback, make necessary adjustments, and update the pull request.

9. **Merge Changes**:
   Once the reviewer is satisfied, they will merge your changes into the main branch.

**Congratulations! You've successfully contributed your feature through a
pull request!**

10. **Delete Local Branch**

    Once Branch is merged you should delete your local branch
    ```bash
    git branch -d feature_branch # This will delete local branch if merged Localy
    git branch -D feature_branch # This will delete local branch even if not merged Localy
    git pull origin main # finally pull latest update from remote repository
    ```


# Resetting in Git: Strategies for Commit, Staging.

When you make a new commit, Git stores a snapshot of your repository at that specific moment in time; later, you can use Git to go back to an earlier version of your project.

## 1. Undo Last Staging
```bash
git reset --mixed # this is the default when executing git reset
```
This will undo the last staging.

## 2. Rename a commit
If there is a typo or want to modify the commit message.
```bash
git commit --amend
# or
git commit --amend -m "message"
```

## 3. Reset to a Commit (Keep Changes)
After staging and commiting your work you might want to go back to the previous commit

```bash
git reset --soft <commit_hash>

# use git log to get commit hash
git log
commit 55c396ac9e3f44510745a79466262df9025f0036 # this is the hash
Author: spikeoze <mukhtaaramiin@gmail.com>
Date:   Tue Dec 5 19:29:13 2023 +0300

    introduction and git workflow
```

This will keep the working in your directory and only reset to the commit specified.

## 4. Reset to a commit (Discard Changes)
This will discard changes be cautious when using this command as it will discard changes after the commit you are resetting to.
```bash
git reset --hard  <commit_hash>
```


