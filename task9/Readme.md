# Git Fundamentals - Task 9
## Working with Remote Repositories and Collaboration
 
---
 
## Objective
- Push a local repository to GitHub
- Create a feature branch and push it to the remote
- Open a Pull Request on GitHub and perform a code review
- Merge the Pull Request on GitHub
- Pull the merged changes back to the local repository
 
---
 
## Steps Performed
 
### Add Files and Commit on Master
```
git add .
git commit -m "added index.html in master"
```
 
---
 
### Push Master to GitHub
```
git push origin master
```
 
---
 
### Create a Feature Branch and Make Changes
```
git checkout -b featureBranch
git add .
git commit -m "implemented button in feature branch"
```
 
---
 
### Push Feature Branch to GitHub
```
git push origin featureBranch
```
 
---
 
### Open a Pull Request on GitHub
 
---
 
### Code Review and Merge on GitHub
- Reviewed the changes in the Pull Request
- Approved and merged `featureBranch` into `master` on GitHub
 
---
 
### Pull the Merged Changes Locally
```
git checkout master
git pull origin master
```
 
---
 
### Verify the Update
The fast-forward message confirmed the remote merge was pulled successfully:
```
Updating 0b62bcf..95a4b8d
Fast-forward
 task9/index.html | 2 +-
```
 
---
 
 