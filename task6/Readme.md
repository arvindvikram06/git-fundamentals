# Git Fundamentals - Task 6
## Stashing Changes for Context Switching

---

## Objective
- Make changes without committing and save them using `git stash`
- Switch branches and perform work on another branch
- Reapply stashed changes using `git stash pop`
- Manage multiple stashes using `git stash list` and `git stash pop stash@{n}`

---

## Steps Performed

### Make Changes and Stash Them
```
git add .
git stash push -m "index file work"
```

---

### View All Stashes
```
git stash list
```

---

### Switch to a Different Branch and Stash Again
```
git checkout -b newBranch
git add .
git stash push -m "about file work"
```

---

### Switch Back to Master and Pop a Specific Stash
```
git checkout master
git stash pop stash@{1}
```

---

### Commit the Popped Changes
```
git commit -m "task 6 completed"
```

---

### Switch to branchA and Pop Remaining Stash
```
git checkout branchA
git stash pop
git commit -m "branchA commit"
```

---

### Merge branchA into Master
```
git checkout master
git merge branchA
```

---

### Verify Final Commit History
```
git log --oneline
```

---

## Git Stash Commands

**`git stash push -m "message"`** — save uncommitted changes with a label

**`git stash list`** — view all saved stashes

**`git stash pop`** — reapply the most recent stash and remove it from the list

**`git stash pop stash@{n}`** — reapply a specific stash by index

**`git stash drop stash@{n}`** — delete a specific stash without applying it

**`git stash clear`** — delete all stashes at once

---

## Why Stashing is Useful

When you are working on changes but need to urgently switch to another branch, you cannot switch with uncommitted changes that conflict. Instead of making a half-done commit, `git stash` lets you temporarily save your work, switch branches freely, do the other work, then come back and reapply exactly where you left off.

---