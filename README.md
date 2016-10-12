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
