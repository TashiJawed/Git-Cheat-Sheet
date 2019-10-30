
# Git Cheat Sheet

### Initialize:
`git init`

### Status:
```
git status
git log
```

### Staging Area:
`git add . `

### Commit:
`git commit -m 'sdf' `

### Reset:
```
git reset (unstage file)
git reset --hard (remove changes whether staged or not, reverts back changes to prev commit)
```

## Gitignore:
**Ignores files wirtten in it. but it needs to be added to git also**

`.gitignore` 

## Chapter 3: Branches

```
git branch (show list of branches)
git branch -v (show list of branches with some detail)
git branch -a (show list of loacal and remote branches)
git branch branch_name (new branch)
git checkout branch_name (switch branch)
```
### Merge:
```
git merge branch_new
git log master..branch_new
```
**OR**
```
git log branch_new..master
```

### Stash:
**Create**

```
git stash (save local changes to stach clipboard)
git stash save <name> (save local changes to stach clipboard with name provided)
git stash list (show list of stashes)
```

**Apply**
git stash pop (apply latest stash and remove it from clipboard)
git stash apply stashname (apply specific stash and will remain saved in clipboard)

### Clone:
`git clone <URL>`

**Make change**
1. Add file by `git add .`
2. Commit file

### Push:
```
git push (push changes to remote repository)

git fetch (fetch changes from remote repo but dont apply it)
git merge (merge changes that was fetch)
```

### Pull:
```
git pull (fetch and merge)
git remote -v (shows remote URLs)
git remote show origin (shows details of origin)
```
### Pull Remote branch:
`git pull <repo name> <branch name>`

### Publish a local repo to Github:
```
1. Create a repo on github
2. git remote add <repo name for e.g origin> https://github....(connects local repo to github)
3. git push -u <repo name> master (-u for first time only)
		Next time
3. git push <repo name> master
```

### Publish local branch to remote repo:
```
git branch work
git checkout work
git push -u <repo name> work
```

### Delete a branch:
```
Local : git branch -d <branch name>
remote: git push -d <repo name> <branch name>
git branch -dr <repo name>/<branch name> (remove local + link to remote branch)
```

##Log:
```
git log (shows log for current branch)
git log <repo name>/master (shows log from remote branch)
```

### Undoing Local Changes(Not commited):
Perticular file
`git checkout HEAD <file/to/restore)`
All files
`git reset --hard HEAD`

### Undoing Commited Changes:

`git revert <commit-hash> (does not actually delete any commit, instead revert changes into a new commit)`
	**OR**
```
git reset --hard <commitHash> (roll back to <commitHash> and discards history)
git reset --keep <commitHash> (roll back but keeps history of commit from which rolling back)
```

### Force Push:
When local commits is behind remote commits after rolling back then git push won't work
beacuse of the diffrence in commits so:

`git push -f <repo name> <branch name>`

### Fast-Forward Commit:
Simple commit. When only one branch is ahead of another branch so merging is simple.

### Merge Commit:
When 2 branches have different commits than how to merge them?
Merge creates an additional commit to bring both branches to same point

### Rebase:
Opposite of merge
When you want to make commits look like a timeline
`git rebase <branch name>`

**For E.g:**

Branch A has commits
Branch B has some other commits
Rebase wil:
1. Discards changes (but save temporarily) of branch A to make it same with branch B
2. will add changes of branch B to branch A 
3. At last will add branch A changes at the end (which was saved temporarily) 








