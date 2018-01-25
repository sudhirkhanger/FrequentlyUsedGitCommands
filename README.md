# FrequentlyUsedGitCommands

## [Version Control with Git](https://in.udacity.com/course/version-control-with-git--ud123)

Create a new repo empty repository in the current directory

	git init
	
Create an identical copy of an existing repository

	git clone <path-to-repository-to-clone>
	
Display current status of the repository

    git status
	
Displays all the commits of a repository including SHA, author, date, and the message

    git log
	
Displays short SHA and the message only

    git log --oneline
	
Displays modified files, number of lines added or removed, and summary

    git log --stat
	
Displays modified files, location of the lines added or removed, and the actual changes

    git log -p
	
Displays information about one particular commit

    git show <SHA1>

Adds the files from the working directory to the staging index aka staging files

    git add <filename>
	
Removes files from the staging index but doesn't delete the actual content

    git rm --cached <file>

Add all files and folders from the current directory

    git add .
	
Saves or records the changes to the repository (from the staging index)

	git commit #Opens the editor
	git commit -m <msg> #Use <msg> as the commit message

Displays files modified, location of lines added/removed, and actual changes

    git diff

Displays all tags

    git tag
	
Creates annotated tags(more info)

    git tag -a v1.0

Add tag to a particular commit

    git tag -a v1.0 <SHA1>

Delete a tag

    git tag -d v1.0
	
Branch

	master - default or the first branch provided by the git
	HEAD - points to the active branch

List all branches

    git branch
	
Create a branch

	git branch <branch-name>
	
Switch to a branch

	git checkout <branch-name>
	
Delete a branch
	
    git branch -d <branch-name>

Force delete a branch with unique commit

    git branch -D <branch-name>
	
Add a branch to commit

    git branch <branch-name> <SHA1>
	
Create and switch to the branch

    git checkout -b <branch-name>
	
Display all branchs in a graph

    git log --oneline --decorate --graph --all

Merge

	* Combining branches together
	* Makes a commit

Combine <branch-name> to the active branch.

    git merge <branch-name>
	
Indicators

	<<<<<<< HEAD everything below this line (until the next indicator) shows you what's on the current branch
    ||||||| merged common ancestors everything below this line (until the next indicator) shows you what the original lines were
	======= is the end of the original lines, everything that follows (until the next indicator) is what's on the branch that's being merged in
	>>>>>>> <branch-name> is the ending indicator of what's on the branch that's being merged in (in this case, the <branch-name> branch)
	
Change the last commit or add/remove the files.

	git commit --amend
	
Reverse a previously made commit

    git revert <SHA>

Ancestry References

	^ - caret
	~ - tilde

    The parent commit – the following indicate the parent commit of the current commit
		HEAD^
		HEAD~
		HEAD~1

	The grandparent commit – the following indicate the grandparent commit of the current commit
		HEAD^^
		HEAD~2

	The great-grandparent commit – the following indicate the great-grandparent commit of the current commit
		HEAD^^^
		HEAD~3

	^ when merged this represents the parent which had HEAD pointed to it. The other branch was merged into this one.
	^2 the second parent or the branch which was merged into the first parent.
	
Erase commits

	Move the head to the parent commit and discarded commit to the working directory.
	git reset --mixed HEAD^
	
	Moves the discarded commit to the staging area
	git reset --soft HEAD^

	Erase commit or move them to the trash
	git reset --hard HEAD^

Make a branch on the current commit

    git branch backup

## [GitHub & Collaboration](https://in.udacity.com/course/github-collaboration--ud456)

    local - your own git repo
    remote - 3rd party git repo which may or may not be local.
    origin - main remote repo

    git remote - manager and interact with the remote repositories.
    	
    git remote add origin git@github.com:sudhirkhanger/my-travel-plans.git - add shortname to the url

    git push -u origin master - send local commits to the remote repo. (git push <remote-shortname> <branch>)
    	
    git remote -v - displays the shortname and url

    git log --oneline --graph --decorate --all

    origin/master - tracking branch - meaning remote origin has master branch at some commit.

    git pull origin master - pull origin's commit to the master branch. Retrieve commits and merge.

    git fetch origin master - pull origin's commit but doesn't merge with master branch.

    _One main point when you want to use git fetch rather than git pull is if your remote branch and your local branch both have changes that neither of the other ones has. In this case, you want to fetch the remote changes to get them in your local branch and then perform a merge manually. Then you can push that new merge commit back to the remote._

    git merge origin/master - merge the origin/master to the current branch.

    git shortlog - how many commits each contributor made

    git shortlog -s -n - number of commits and dev name 

    git log --author=<contributor name> - list all commits by contributor name

    git log --grep=<search> - search commits with search term search

    git rebase -i HEAD~3 - base to the 4th commit. squash 3 commits into one.

    git push -f - force push
	
## Misc

    git reset --hard HEAD

    git remote show branch
    
    git branch -r
    
    git branch -a
    
    git branch -vv
    
    git branch -v
    
set new url

    git remote set-url origin new-url

Remove files after adding .gitignore

    git rm -r --cached . 
    git add .
    git commit -m 'Removed all files that are in the .gitignore' 
    git push origin master

Git Stash

    git stash
    git stash list
    git stash drop

Git Checkout

    git checkout branch-name

Git remove files

    git rm file1.txt
    git commit -m "remove file1.txt"

    remove from git but not from file system
    git rm --cached file1.txt

    git push origin master

## [Think Like a Git](http://think-like-a-git.net)

    to list all commits in your repository at the command line
    git log --oneline --abbrev-commit --all

    git log --oneline --abbrev-commit --all --graph

    If you want to see branch and tag labels, add --decorate:
    git log --oneline --abbrev-commit --all --graph --decorate

    git log --oneline --abbrev-commit --all --graph --decorate --color

