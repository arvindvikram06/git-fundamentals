# Git Fundamentals - Task 3
## Undoing Changes and Reverting Commits

---

## Objective
- Modify a tracked file and undo changes before staging
- Make a commit and undo it safely using `git revert`
- Use `git reset` to move the branch pointer back
- Understand the difference between `revert` and `reset`

---

## Steps Performed

### Modify a Tracked File and Check Status
```
git status
git diff
```

---

### Undo Unstaged Changes
```
git restore task3/index.html
```

---

### Stage and Commit Changes
```
git add .
git commit -m "added changes"
```

---

### Verify Commit History
```
git log --oneline
```

---

### Revert the Commit Safely
```
git revert HEAD
```

---

### Reset to Undo the Revert Commit
```
git reset --soft HEAD~1
```

---

### Verify Final Commit History
```
git log --oneline
```

---

## Git Commands for Undoing Changes

**git restore**
- Undoes changes in the working directory or staging area
- Works at file level, does not create a new commit
- Example: `git restore index.html`

**git checkout**
- Undoes changes in the working directory (deprecated for this purpose)
- Works at file level, does not create a new commit
- Example: `git checkout -- index.html`

**git revert**
- Reverts a specific commit by creating a new commit
- Safe to use on shared/pushed branches
- Example: `git revert HEAD`

**git reset --soft**
- Moves the branch pointer back, keeps changes staged
- Does not create a new commit
- Example: `git reset --soft HEAD~1`

**git reset --mixed** (default)
- Moves the branch pointer back, keeps changes in working directory but unstaged
- Does not create a new commit
- Example: `git reset --mixed HEAD~1`

**git reset --hard**
- Moves the branch pointer back and discards all changes permanently
- Does not create a new commit, avoid using after pushing
- Example: `git reset --hard HEAD~1`

---