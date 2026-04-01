# Git Fundamentals - Task 5
## Interactive Rebasing of Commit History

---

## Objective
- Create a series of commits with minor changes
- Use `git rebase -i` to squash multiple commits into one
- Edit and clean up commit messages
- Understand how squashing helps before merging into main

---

## Steps Performed

### Create File and Make Multiple Commits
```
git add .
git commit -m "first commit"

git add .
git commit -m "added a line to index commit 2"

git add .
git commit -m "added a line to index commit 3"
```

---

### Verify Commit History Before Rebase
```
git log --oneline
```

---

### Start Interactive Rebase on Last 3 Commits
```
git rebase -i HEAD~3
```

---

### Squash Commits in the Editor

Changed the rebase file from:
```
pick ae9d758 first commit
pick f8ae757 added a line to index commit 2
pick 6939748 added a line to index commit 3
```

To:
```
pick ae9d758 first commit
squash f8ae757 added a line to index commit 2
squash 6939748 added a line to index commit 3
```

---

### Wrote the Final Combined Commit Message
```
first commit
```

---

### Verify Cleaned Up History After Rebase
```
git log --oneline
```

3 commits were squashed into 1 clean commit.

---

### Push to GitHub
```
git push origin master
```

---

## Interactive Rebase Commands

**`pick`** — keep the commit as is

**`reword`** — keep the commit but edit its message

**`squash`** — combine this commit into the previous one

**`fixup`** — same as squash but discards the commit message

**`drop`** — delete the commit entirely

---

## Why Squashing Helps

Before squashing the history looked like:
```
added a line to index commit 3
added a line to index commit 2
first commit
```

After squashing:
```
final merged
```

Squashing combines multiple small or work-in-progress commits into one meaningful commit. This keeps the main branch history clean and readable, making it easier to understand what changed and why.

---