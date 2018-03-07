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

Naming convention

    local - your local git repository
    remote - 3rd party git repo which may or may not be local.
    origin - main remote repo. Or the forked repository
	upstream - source or the original repository where origin was forked from.
	
Manage and interact with the remote repositories

    git remote
	
Display full path to the remote repository

    git remote -v
	
Add shortname and the remote url to the local repo	
    	
    git remote add origin git@github.com:sudhirkhanger/my-travel-plans.git - add shortname to the url

Send local commits to the remote repo.

	git push -u <remote-shortname> <branch>

Tracking branch

    origin/master - remote branch origin has a master branch at some commit. Tracks the progress of the master branch on the remote branch origin.
	
Sync remote repository with the local

	// pulls remote branch origin's commit to the master branch. Merge happens.
    git pull origin master
	
Retrive commits from the remote branch and without merge

	// fetch all branches of the origin
	git fetch origin
	// fetch origin's commits from master branch
    git fetch origin master
	// merge origin/master with the current branch
	git merge origin/master

Number of commits made by each contributor

	git shortlog
	
List contributor name and number of commits

    git shortlog -s -n

Filter commits by author name

    git log --author=<contributor name>
	
Filter commits by search query

    git log --grep=<search>

Change shortnames

	git remote rename <new-name> <existing-name>
	
Retrieving Upstream Changes
	
	// add the source repository
	git remote add upstream <url-of-the-source-repository>

	// fetches changes from the upstream source repository
	// upstream/master - tracks where upstream's master branch is

	// fetch all branches of the upstream
	git fetch upstream

	// fetch upstream's commits from master branch
	git fetch upstream master
	
	// to sync to your fork merge into a local branch and push it to the origin
	git checkout master
	git merge upstream/master
	git push origin master
	
Squash commits

	// move commits to a new base. Squash three commits into one
	// HEAD~3 HEAD~2 HEAD~1 HEAD
    git rebase -i <base for example HEAD~3>
	
Force push a branch

	git push -f <remote-branch> <local-branch>
	
## [Think Like a Git](http://think-like-a-git.net)

    to list all commits in your repository at the command line
    git log --oneline --abbrev-commit --all

    git log --oneline --abbrev-commit --all --graph

    If you want to see branch and tag labels, add --decorate:
    git log --oneline --abbrev-commit --all --graph --decorate

    git log --oneline --abbrev-commit --all --graph --decorate --color
	
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

Git remove files

    git rm file1.txt
    git commit -m "remove file1.txt"

    remove from git but not from file system
    git rm --cached file1.txt

    git push origin master
