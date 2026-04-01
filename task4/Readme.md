# Git Fundamentals - Task 4
## Simulating and Resolving Merge Conflicts
 
---
 
## Objective
- Create two branches from the same commit
- Modify the same file in both branches to cause a conflict
- Attempt to merge and observe the conflict
- Resolve the conflict manually using VS Code
- Use `git status` and `git diff` to identify conflicting changes
 
---
 
## Steps Performed
 
### Create and Switch to branchA
```
git checkout -b branchA
```
 
---
 
### Make Changes and Commit in branchA
```
git add .
git commit -m "created changed in index file in branchA"
```
 
---
 
### Switch to Master and Create branchB
```
git checkout master
git checkout -b branchB
```
 
---
 
### Make Changes and Commit in branchB
```
git add .
git commit -m "modified index file from branchB"
```
 
---
 
### Switch to Master and Merge branchA
```
git checkout master
git merge branchA
```
 
---
 
### Check Conflict Status and Diff
```
git status
git diff
```
 
---
 
### Stage and Commit the Resolved Merge
```
git add .
git commit -m "mergedA"
```
 
---
 
### Merge branchB into Master
```
git merge branchB
```
 
---
 
### Resolve Second Conflict and Commit
```
git add .
git commit -m "merged branchB to master"
```
 
---
 
### Verify Final Commit History
```
git log --oneline
```
 
---
 
## What Happens During a Merge Conflict
 
When two branches modify the same line in a file, Git cannot decide which change to keep and marks the file with conflict markers.
 
**`<<<<<<< HEAD`** — start of the current branch's version
 
**`=======`** — divider between the two versions
 
**`>>>>>>> branchA`** — end of the incoming branch's version
 
The conflict must be resolved manually by editing the file, removing the markers, and keeping the desired content.
 
---