# Comprehensive Git Workflow with Forced Push and Recovery

## Objective
To simulate an advanced Git workflow involving:
- Multiple branches (feature, bugfix, release)
- History rewriting using interactive rebase
- Forced push (`git push --force`)
- Recovery of lost commits using `git reflog`
- Understanding best practices for team collaboration

---

## Repository Setup

Initialized a Git repository and created multiple branches:

```bash
git init
git branch feature/nav
git branch bugfix/card
git branch release/v1
```

Branches used:
- `master` → main codebase  
- `feature/nav` → feature development  
- `bugfix/card` → bug fixing  
- `release/v1` → release preparation  

---

## Feature Development

Worked on `feature/nav` branch and created multiple commits:

```bash
git checkout feature/nav

echo "Home button" >> index.html
git commit -am "added home button"

echo "About button" >> index.html
git commit -am "added about button"
```

---

## Interactive Rebase (History Rewriting)

Used interactive rebase to clean commit history:

```bash
git rebase -i HEAD~2
```

- Squashed multiple commits into one  
- Created a cleaner, more readable history  

---

## Push Rejection (Non-Fast-Forward)

After rewriting history, attempted normal push:

```bash
git push origin feature/nav
```

Result:
- Push rejected due to history mismatch (non-fast-forward)

---

## Forced Push

Used force push to overwrite remote history:

```bash
git push --force origin feature/nav
```

- Replaced remote branch history with rewritten local history  

---

## Mistake Simulation (Data Loss)

Simulated accidental data loss:

```bash
git reset --hard HEAD~1
git push --force origin feature/nav
```

- Deleted latest commit  
- Force pushed → commit removed from remote  

---

## Recovery Using git reflog

Used reflog to recover lost commit:

```bash
git reflog
```

Example:

```
200b59d HEAD@{1}: rebase (finish)
```

Recovered using:

```bash
git checkout 200b59d
git checkout -b recovered-feature/nav
```

---

## Restoring Original Branch

Restored the broken branch using recovered data:

```bash
git checkout feature/nav
git reset --hard recovered-feature/nav
git push origin feature/nav
```

- Successfully restored lost commits  
- Synced with remote repository  

---

- `git rebase` rewrites commit history  
- `git push --force` overwrites remote history  
- Forced push can lead to data loss  
- `git reflog` acts as a safety net to recover lost commits  
- Always verify before performing destructive operations  

---

