# FrequentlyUsedGitCommands

These are my frequently used Git commands.

    git reset --hard HEAD

    git remote show branch
    
    git branch -r
    
    git branch -a
    
    git branch -vv
    
    git branch -v
    
    git remote -v

## Set new url

    git remote set-url origin new-url

## Remove files after adding .gitignore

    git rm -r --cached . 
    git add .
    git commit -m 'Removed all files that are in the .gitignore' 
    git push origin master

## Git Stash

    git stash
    git stash list
    git stash drop

## Git Checkout

    git checkout branch-name

## Commands fromt he Udacity's Version Control with Git course

git status - status

git log - info about existing commits

git show - info about a given commit commit id or sha

git log --oneline show log in one lines.

git log --stat - files changed, insertions, deletions, etc.

git log -p - detailed changes.

git add filename - add the file to staging index

git rm --cached <file> - remove the file from the staging index without deleting

git add . - add all files recursively from the current directory

git commit -m "Initial commit" - only message and no description

git diff - look at changes made but not committed

git tag -a v1.0 - add tag v1.0 to the latest commit (-a stands for annotated tag)

git tag - display all tags

git tag -d v1.0 - delete the tags

git tag -a v1.0 a87984 - Adding A Tag To A Past Commit

git branch - list all branches 

git branch branch-name - create a branch

git checkout sidebar - switch to branch sidebar

git branch -d sidebar - delete the branch sidebar

git branch -D sidebar - force delete when there is a commit

git merge <name-of-branch-to-merge-in>

git commit --amend - alter the most-recent commit

git revert <SHA-of-commit-to-revert> - will undo the changes that were made by the provided commit and creates a new commit to record the change

git branch backup - backs up

git reset --mixed HEAD^ - move the parent commit to working directory

git reset --soft HEAD^ - moves the parent commit to the staging area

git reset --hard HEAD^ - erases the parent commit 

^ – indicates the parent commit
~ – indicates the first parent commit

the parent commit – the following indicate the parent commit of the current commit
HEAD^
HEAD~
HEAD~1
the grandparent commit – the following indicate the grandparent commit of the current commit
HEAD^^
HEAD~2
the great-grandparent commit – the following indicate the great-grandparent commit of the current commit
HEAD^^^
HEAD~3

[Version Control with Git](https://in.udacity.com/course/version-control-with-git--ud123)
