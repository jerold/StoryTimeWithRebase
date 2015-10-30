# StoryTimeWithRebase
Clean up your history, and tell a better story.


will change history & delete commits, create a new branch from HEAD before doing this to create a branch backup

you can break your history if you try to change commits that have been pushed to a remote origin. But whatever, git 
push --force FTW 

# Amending and Rewriting History:

Add staged changes to the previous commit, allows you to also update commit message
```
git commit --amend
```

Rewrite history, allows us to change the history of commits between parent and HEAD
Operations:
- squash : merge commit with the one above it, can update commit message
- fixup  : merge commit with the one above it, use commit message from above commit
```
git rebase -i <parent>
```

# Staying up to date:

bring changes in one branch into the current one as a special commit "Merge branch master into my-branch"
merging too often will complicate your commit log
```
git checkout my-branch
git merge master
```

takes current branch and rebuilds it on top of the source branch
won't get extra merge commits in branch (clutter)
rebase will break things if your commits have already been pushed, duh, you are changing history!
```
git checkout my-branch
git rebase master
```
