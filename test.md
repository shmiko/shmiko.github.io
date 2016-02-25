These are some common git commands and their meaning: These will be used when interacting with remote repositories on GitHub

Initialise a repository
'git init' - from within current working directory

Clone a remote repository
'git clone git@github.com/shmiko/CMI' - run from directory where you want the cloned repo folder to exist. eg: To end up with folder structure like root/CMI you would run the command from root which will create the CMI directory, then change to the new directory using the cd command.

Add existing local folder to remote repository
'git remote add origin remote repository URL'

Add files to the remote repo
'git add .' - this is run from current working directory. This command will add all changes files.

Commit changed files to remote repo
'git commit -m "comment"' - The -m stands for message, this message is attached to the commit.

Shortcut to add and commit
'git commit -a -m "comment"' - This will add all recently edited files and commit them at the same time.

Push changes to remote repo
'git push origin master' - Assumes you are using the master branch.

Remove last commit
'git reset --soft HEAD~1' - once run add the files again and rerun commit.

Check status of current branch
'git status' - this will list any pending changes, or will suggest the branch is clean with no pending changes. This will also allow you to check which branch you are working in.

Check branch
'git branch' - This will list all branches with the current branch a different color and with an asterix on the left.

Change branch
'git checkout branchname' - Once run you will now be working in the branch selected in the command.

Merge branch
'git merge branchname' - Assume you want to merge branchname to master, you first change to master using 'git checkout master' then run this command to merge branchname into master.
take note
- When merging branches you might get confilct as reported by github, if so you will need to resolve the issues locally and re commit the files. most of the time if you have bene careful the merge will successfully merge without interaction, at other times you will be promted to comment the commited changes pending by the merge process.


See merged branches
'git branch --merged'





See unmerged branches
'git branch --no-merge'

Delete a branch
'git branch -d branchname' - the -d denotes Delete

Force delete of a branch
'git branch -D branchname' - the -D will force Delete the branch
These are just a small set of git commands but for me have been the most commonly used when interacting with Github.
