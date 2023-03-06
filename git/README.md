# Git

### Init
###### to setup git file on a new project

`$ git init`

##

### Add
###### For the whole directory
`$ git add .`

###### To specify the changes
`$ git add -p client/src/App.js`

##

### Status
`$ git status`

##

### Log
`$ git log`

##

### Branch
###### check all branches and what branch currently using
`$ git branch`

###### To delete branch locally
`$ git branch -d <branch/name>`

##

### Checkout
###### To create and switch
`$ git checkout -b <new-branch-name`

###### To switch
`$ git checout <branch-name>`

##

### Commit
`$ git commit -m "change label"`

##

### Pull
`$ git pull origin <branch-name>`

###### or
`$ git pull`

###### To pull even you have already made the changes, it will stack the local commit on top of it
`$ git pull --rebase`

###### or 
`$ git pull -r`

### Push
###### to push
`$ git push`

##### to specific branch
`$ git push origin fix/change-label`

###### Push Force
`$ git push --force`

##

### Stash
###### To store your current codes
`$ git stash`

###### To put it back
`$ git stash pop`

##

### Log
###### To check history
`$ git log`

###### To go back on the specific commit
`$ git checkout <commit-hash>`

###### for instance you're in the specific current branch and commit:
```
$ git status
$ git stash
$ git log
$ git checkout b29d899acac1ae103ff7679f6992e2574fa9ea73
```

##

### Reset: Undoing commits
###### To reset:

###### To remove most current commit, take note: the number 1 specify the latest

`$ git reset --hard HEAD~1`

###### To remove the current commit but don't want to remove the codes/changes

`$ git reset --soft HEAD~1`

##

### Commit Ammend: Changing commits
###### To add or merge on the previous commit before pushing
```
$ git add .
$ git commit --amend
```

##

### Revert
```
$ git log
$ git revert <commit-hash>
$ git push
```

##

### Merge
###### merging via terminal
```
$ git checkout main
$ git merge main
```

##



### Git
###### Installation
`$ sudo apt install git`

##


[main c662b29] vscode ubuntu
 Committer: Joseph Sallao <sep@kimat-pop.bbrouter>
Your name and email address were configured automatically based
on your username and hostname. Please check that they are accurate.
You can suppress this message by setting them explicitly. Run the
following command and follow the instructions in your editor to edit
your configuration file:

    git config --global --edit

After doing this, you may fix the identity used for this commit with:

    git commit --amend --reset-author

 1 file changed, 13 insertions(+), 1 deletion(-)