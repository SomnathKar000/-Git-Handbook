# Learning Git Faster

A curated list of essential Git commands and resources to help you learn Git faster.

## Table of Contents

1. [Core](#core)
2. [Branching](#branching)
3. [Merging](#merging)
4. [Stashing](#stashing)
5. [Remotes](#remotes)
6. [Configuration](#configuration)
7. [Plumbing](#plumbing)
8. [Porcelain](#porcelain)
9. [Alias](#alias)
10. [Hook](#hook)
11. [Experimental](#experimental)

## Core

- `git init`
- `git clone`
- `git add`
- `git commit`
- `git status`
- `git diff`
- `git checkout`
- `git reset`
- `git log`
- `git show`
- `git tag`
- `git push`
- `git pull`

## Branching

- `git branch`
- `git checkout -b`
- `git merge`
- `git rebase`
- `git branch --set-upstream-to`
- `git branch --unset-upstream`
- `git cherry-pick`

## Merging

- `git merge`
- `git rebase`

## Stashing

- `git stash`
- `git stash pop`
- `git stash list`
- `git stash apply`
- `git stash drop`

## Remotes

- `git remote`
- `git remote add`
- `git remote remove`
- `git fetch`
- `git pull`
- `git push`
- `git clone --mirror`

## Configuration

- `git config`
- `git global config`
- `git reset config`

## Plumbing

- `git cat-file`
- `git checkout-index`
- `git commit-tree`
- `git diff-tree`
- `git for-each-ref`
- `git hash-object`
- `git ls-files`
- `git ls-remote`
- `git merge-tree`
- `git read-tree`
- `git rev-parse`
- `git show-branch`
- `git show-ref`
- `git symbolic-ref`
- `git tag --list`
- `git update-ref`

## Porcelain

- `git blame`
- `git bisect`
- `git checkout`
- `git commit`
- `git diff`
- `git fetch`
- `git grep`
- `git log`
- `git merge`
- `git push`
- `git rebase`
- `git reset`
- `git show`
- `git tag`

## Alias

- `git config --global alias.<alias> <command>`

## Hook

- `git config --local core.hooksPath <path>`

## Experimental

- `git annex`
- `git am`
- `git cherry-pick --upstream`
- `git describe`
- `git format-patch`
- `git fsck`
- `git gc`
- `git help`
- `git log --merges`
- `git log --oneline`
- `git log --pretty=`
- `git log --short-commit`
- `git log --stat`
- `git log --topo-order`
- `git merge-ours`
- `git merge-recursive`
- `git merge-subtree`
- `git mergetool`
- `git mktag`
- `git mv`
- `git patch-id`
- `git p4`
- `git prune`
- `git pull --rebase`
- `git push --mirror`
- `git push --tags`
- `git reflog`
- `git replace`
- `git reset --hard`
- `git reset --mixed`
- `git revert`
- `git rm`
- `git show-branch`
- `git show-ref`
- `git show-ref --heads`
- `git show-ref --tags`
- `git stash save`
- `git subtree`
- `git tag --delete`
- `git tag --force`
- `git tag --sign`
- `git tag -f`
- `git tag -l`
- `git tag --verify`
- `git unpack-file`
- `git update-index`
- `git verify-pack`
- `git worktree`

### Resources to Learn Git Faster

1. [Git Official Documentation](https://git-scm.com/doc)
2. [GitHub Learning Lab](https://rb.gy/ksc45f)
3. [Codecademy Course](https://codecademy.com/learn/learn-git)
4. [Pro Git: by Scott Chacon [Book]](https://git-scm.com/book/en/v2)
5. [FreeCodeCampOrg- Beginner](https://rb.gy/ljxt5s)
6. [FreeCodeCampOrg- Intermediate](https://rb.gy/1x6mc)
7. [Programming with Mosh](https://rb.gy/vfkom)

## Difference between git pull & git fetch

`git pull` and `git fetch` are both Git commands used to retrieve changes from a remote repository, but they differ in how they integrate those changes into the local repository. Let's explore the differences with examples:

### `git fetch`:

- **Purpose:** Fetches changes from a remote repository to the local repository, but it does not automatically merge or rebase them into the working branch.
- **Usage:**
  ```bash
  git fetch origin
  ```
- **Example Workflow:**

  ```bash
  # Fetch changes from the remote repository
  git fetch origin

  # View the changes fetched
  git log origin/master

  # Merge the fetched changes into the local branch (if desired)
  git merge origin/master
  ```

### `git pull`:

- **Purpose:** Fetches changes from a remote repository and automatically merges or rebases them into the working branch.
- **Usage:**
  ```bash
  git pull origin master
  ```
- **Example Workflow:**
  ```bash
  # Fetch and merge changes from the remote repository into the current branch
  git pull origin master
  ```

### Differences:

1. **Automatic Integration:**

   - `git fetch` fetches changes but leaves them in the remote-tracking branches (e.g., `origin/master`), and you need to explicitly merge or rebase.
   - `git pull` fetches and integrates changes automatically, either by merging or rebasing.

2. **Workflow:**

   - With `git fetch`, you have more control over how and when you integrate changes.
   - `git pull` is a shortcut that combines `git fetch` and either `git merge` or `git rebase`.

3. **Commit History:**

   - `git fetch` does not modify your local branches, preserving your commit history.
   - `git pull`, especially with rebase, can rewrite commit history as it integrates changes.

4. **Safety:**
   - `git fetch` is safer in a collaborative environment, as it allows you to review changes before integration.
   - `git pull` may automatically merge changes, which could lead to conflicts that need to be resolved.

### Example Scenario:

Suppose you're working on a branch named `feature-branch` and want to update it with changes from the remote `master` branch:

- **Using `git fetch` and merge:**

  ```bash
  git fetch origin        # Fetch changes
  git merge origin/master # Merge changes into your local branch
  ```

- **Using `git pull`:**
  ```bash
  git pull origin master  # Fetch and automatically merge changes
  ```

In summary, use `git fetch` when you want to review changes before integrating them, and use `git pull` when you want a quick way to fetch and integrate changes automatically. The choice depends on your workflow and the level of control you want over the integration process.

## Difference between `git merge` & `git reset`

`git merge` and `git reset` are both Git commands that are used for different purposes in managing changes within a Git repository. Let's explore the differences between them with examples:

### `git merge`:

- **Purpose:** Combines changes from different branches, integrating them into the current branch.
- **Usage:**
  ```bash
  git merge <branch-name>
  ```
- **Example Workflow:**

  ```bash
  # Switch to the branch where you want to merge changes
  git checkout target-branch

  # Merge changes from the source branch
  git merge source-branch
  ```

### `git reset`:

- **Purpose:** Resets the current branch to a specified commit, either preserving or discarding changes.
- **Usage:**
  ```bash
  git reset <commit>
  ```
- **Example Workflow (Discarding Changes):**
  ```bash
  # Reset the branch to a specific commit, discarding changes
  git reset --hard <commit>
  ```
- **Example Workflow (Preserving Changes):**
  ```bash
  # Reset the branch to a specific commit, preserving changes as uncommitted
  git reset --soft <commit>
  ```

### Differences:

1. **Operation:**

   - `git merge` combines changes from different branches, creating a new commit that reflects the integration of changes.
   - `git reset` moves the branch pointer to a specified commit, potentially discarding or preserving changes.

2. **Commit History:**

   - `git merge` introduces a new commit to represent the integration of changes, preserving the commit history of both branches.
   - `git reset` modifies the commit history by moving the branch pointer, potentially discarding commits (with `--hard`) or preserving them as uncommitted changes (with `--soft`).

3. **Branches:**
   - `git merge` is typically used to merge changes between branches.
   - `git reset` is often used for undoing commits or resetting the branch pointer.

### Example Scenario:

Suppose you have a feature branch (`feature-branch`) and you want to integrate its changes into the main branch (`main`). You have two options:

- **Using `git merge`:**

  ```bash
  git checkout main         # Switch to the main branch
  git merge feature-branch  # Merge changes from feature-branch into main
  ```

- **Using `git reset` to undo changes:**
  ```bash
  git checkout main         # Switch to the main branch
  git reset --hard feature-branch  # Discard changes and move main pointer to feature-branch
  ```
  In this case, the `--hard` option discards all changes, including those made in the `feature-branch`. Be cautious when using `--hard` as it permanently discards changes.

Choose between `git merge` and `git reset` based on your desired outcome and the nature of the changes you want to integrate or undo.
