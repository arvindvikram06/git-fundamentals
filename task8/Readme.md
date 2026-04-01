# Git Fundamentals - Task 10
## Using Git Hooks for Automated Checks
 
---
 
## Objective
- Create a pre-commit hook in the `.git/hooks` directory
- Write a shell script that checks for `console.log` statements
- Ensure the commit is aborted if the check fails
- Understand how Git hooks improve code quality
 
---
 
## Steps Performed
 
### View Available Hooks
```
ls .git/hooks
```
 
---
 
### Create the pre-commit Hook
```
nano .git/hooks/pre-commit
```
 
---
 
### Hook Script
```bash
#!/bin/sh
 
echo "Running pre-commit checks..."
 
if grep -r "console.log" task8/; then
  echo "ERROR: Remove console.log statements before committing."
  exit 1
fi
 
echo "All checks passed!"
exit 0
```
 
---
 
### Make the Hook Executable
```
chmod +x .git/hooks/pre-commit
```
 
---
 
### Test the Hook (Fail Case)
```
git commit -m "implemented add function in script"
```
 
Output:
```
Running pre-commit checks...
task8/script.js:    console.log("hello");
ERROR: Remove console.log statements before committing.
```
 
Commit was aborted automatically.
 
---
 
### Fix the Issue and Commit Again
Removed the `console.log` line from `script.js`, then:
```
git commit -m "implemented add function in script"
```
 
Output:
```
Running pre-commit checks...
All checks passed!
[master 55684c9] implemented add function in script
```
 
---
 
## How Git Hooks Improve Code Quality
 
**Prevents bad code from entering the repo** — checks run automatically before every commit
 
**Saves review time** — reviewers focus on logic, not style issues
 
**Enforces team standards** — every developer follows the same rules automatically
 
**Cannot be skipped accidentally** — hook runs in the background on every commit
 
---
 