---
layout: post
section-type: post
title: Starting with GitHub Basics
categories: ['tech']
tags: [ 'tutorial' ]
---




### Starting with Git
<span class="left-justified">
These are some common git commands and their meaning:
These will be used when interacting with remote repositories on [GitHub](http://github.com)
</span>

<span class="left-justified">
1. Initialize a repository - '<span class="blue">git init</span>' - from within current working directory.
</span>

<span class="left-justified">
2. Clone a remote repository - '<span class="blue">git clone git@github.com/user/repo</span>' - run from directory where you want the cloned repo folder to exist. **eg:** To end up with folder structure like root/CMI you would run the command from root which will create the CMI directory, then change to the new directory using the cd command.
</span>

<span class="left-justified">
3. Add existing local folder to remote repository - '<span class="blue">git remote add origin remote repository URL</span>'.
</span>

<span class="left-justified">
4. Add files to the remote repo - '<span class="blue">git add.</span>' - this is run from current working directory. This command will add all changes files.
</span>

<span class="left-justified">
5. Commit changed files to remote repo - '<span class="blue">git commit -m "comment"</span>' - The -m stands for message, this message is attached to the commit.
</span>

<span class="left-justified">
6. Shortcut to add and commit - '<span class="blue">git commit -a -m "comment"</span>' - This will add all recently edited files and commit them at the same time.
</span>

<span class="left-justified">
7. Push changes to remote repo - '<span class="blue">git push origin master</span>' - Assumes you are using the master branch.
</span>

<span class="left-justified">
8. Remove last commit - '<span class="blue">git reset --soft HEAD~1</span>' - once run add the files again and rerun commit.
</span>

<span class="left-justified">
9. Check status of current branch - '<span class="blue">git status</span>' - this will list any pending changes, or will suggest the branch is clean with no pending changes. This will also allow you to check which branch you are working in.
</span>

<span class="left-justified">
10. Check branch - '<span class="blue">git branch</span>' - This will list all branches with the current branch a different color and with an asterisk on the left.
</span>

<span class="left-justified">
11. Change branch - '<span class="blue">git checkout branchname</span>' - Once run you will now be working in the branch selected in the command.
</span>

<span class="left-justified">
12. Merge branch - '<span class="blue">git merge branchname</span>' - Assume you want to merge branchname to master, you first change to master using 'git checkout master' then run this command to merge branchname into master. **take note** - When merging branches you might get conflict as reported by github, if so you will need to resolve the issues locally and re commit the files. most of the time if you have bene careful the merge will successfully merge without interaction, at other times you will be prompted to comment the commited changes pending by the merge process.
</span>

<span class="left-justified">
13. See merged branches - '<span class="blue">git branch --merged</span>' - This will list all branches which have been merged.
</span>

<span class="left-justified">
14. See un-merged branches - '<span class="blue">git branch --no-merge</span>' - This will list all branches yet to be merged.
</span>

<span class="left-justified">
15. Delete a branch - '<span class="blue">git branch -d branchname</span>' - the -d denotes Delete.
</span>

<span class="left-justified">
16. Force delete of a branch - '<span class="blue">git branch -D branchname</span>' - the -D will force Delete the branch.
</span>

[![GitHub](../../../../../../img/labtocat.png)](http://github.com)


These are just a small set of git commands but for me have been the most commonly used when interacting with Github.
