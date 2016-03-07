---
layout: post
section-type: post
title: Starting with Markdown Basics
categories: ['tech']
tags: [ 'tutorial' ]
---




### Markdown Basics
<span class="left-justified">
- Markdown is commonly used for README files on GitHub as well as for many blogging frameworks such as Jekyll.  
- It is automatically converted to HTML whilst using simple punctuation syntax and characters and can be written in any text editor. You can also use an online editor such as [markable](http://markable.in/editor/), or even edit directly via [github](http://github.com).  
- Files should be saved as .txt or the native format of .md</span>  

<hr />

<pre><code></code></pre>

### Creating Headings
<span class="left-justified">
Use hash symbols and a space, with the number of hashes equal to the heading style when thinking in terms of HTML 'h' tags. For instance \<h1> headings would be written as a single hash and a space '# ', whilst an \<h4> would be written with 4 hashes and a space like this '#### '.  
Here are some actual examples:
</span>  

# Heading 1

## Heading 2

###### Heading 6
<pre><code></code></pre>

### Paragraphs
<span class="left-justified">
A paragraph is just normal lines of text.  
If you wanted to have a single line break you would use 2 or more spaces with a return.  
A new paragraph would be created by adding 1 or more bank lines.
</span>  
<pre><code></code></pre>  


### Bold and/or italic text
<span class="left-justified">
Bold or strong text will have 2 asterisks on both side of the **text**.  
Italic or emphasized text will have a single asterisk on both sides of the *text*.  </span>
<span class="left-justified">
To combine effects of bold and italic use 3 asterisks on both sides of the ***text***.
</span>  
<pre><code></code></pre>

### Creating Lists
==================   

<span class="left-justified">
Ordered lists are created simply by starting with the line number followed by a dot.
</span>
1. Line 1
2. Line 2  

<span class="left-justified">
Unordered lists are created by starting with a hyphen followed by a space.
</span>
- Line 1
- Line 2  
<pre><code></code></pre>

### Blockquotes
<span class="left-justified">
Blockquotes are created by starting with a caret or greater than symbol followed by a space.
</span>
> Blockquote text


---


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
