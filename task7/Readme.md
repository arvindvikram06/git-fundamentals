# Git Fundamentals - Task 7
## Cherry-Picking Commits Between Branches

---

## Objective
- Create two branches with distinct commits
- Identify specific commits to apply to another branch
- Use `git cherry-pick` to selectively apply commits
- Handle conflicts that arise during cherry-pick
- Verify commit history after cherry-picking

---

## Steps Performed

### Make Commits on newBranch
```
git checkout newBranch
git add .
git commit -m "commit 1 from newBranch"

git add .
git commit -m "commit 2 from newBranch"

git add .
git commit -m "commit 3 from newBranch"
```

---

### View Commit History on newBranch
```
git log --oneline
```
---

### Add another Commit on newBranch
```
git checkout newBranch
git add .
git commit -m "about page from newBranch"
```

---

### Cherry-Pick the Clean Commits onto Master
```
git checkout master
git cherry-pick 3a76a3b 6531a5b
```

---

### Verify Final Commit History
```
git log --oneline
```

Cherry-picked commits now appear in master's history.

---

## What is Cherry-Pick

`git cherry-pick <hash>` takes a specific commit from any branch and applies it to your current branch. Unlike merging which brings in all commits from a branch, cherry-pick lets you pick only the exact commits you want.

**Cherry-pick multiple commits at once:**
```
git cherry-pick <hash1> <hash2>
```
