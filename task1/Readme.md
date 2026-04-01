# Git Fundamentals - Task 1  
## Initialize, Commit, Branch, and Merge

---

##  Objective
- Initialize a new Git repository  
- Create files and commit them  
- Create a new branch and make changes  
- Merge the branch back into the main branch  
- Verify commit history  

---

## Steps Performed

### Initialize Repository
git init

---

### Create Files and Commit
git add .  
git commit -m "created index.html and added h1"

---

### Create and Switch to a New Branch
git checkout -b h2feature

---

### Make Changes and Commit in Branch
git add .  
git commit -m "implemented h2 tag and style.css"

---

### Push Branch to GitHub
git push origin h2feature

---

### Switch Back to Main Branch
git checkout master

---

### Merge Feature Branch into Main
git merge h2feature

---

### Verify Commit History
git log --graph --decorate

---
