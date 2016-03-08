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

---  

### Creating Headings  

<span class="left-justified">
Use hash symbols and a space, with the number of hashes equal to the heading style when thinking in terms of HTML 'h' tags. For instance h1 headings would be written as a single hash and a space '# ', whilst an h4 would be written with 4 hashes and a space like this '#### '.  
Here are some actual examples:
</span>  

```
# Heading 1

## Heading 2

###### Heading 6
```   
Results in the following headings

# Heading 1

## Heading 2

###### Heading 6  


### PreCode Blocks :+1:
  - Using 3 backticks and the code language will produce the following code block tags. This is for GFM.   
  For other markdown supposedly you can use 4 spaces or a tab but I have yet to see it work.  
  Javascript example is started off like this:
```
```javascript
   var object = {};
```
which can result like this:
```
  var object = {};
```
An HTML example would start like this:
```  
```html
    Code
```
which results in HTML like this:
```html
<pre><code>Code</code></pre>
```

### Paragraphs
<span class="left-justified">
A paragraph is just normal lines of text.  
If you wanted to have a single line break you would use 2 or more spaces with a return.  
A new paragraph would be created by adding 1 or more bank lines.
</span>  



### Bold and/or italic text
<span class="left-justified">
Bold or strong text will have 2 asterisks on both side of the **text**.  
Italic or emphasized text will have a single asterisk on both sides of the *text*.  </span>
<span class="left-justified">
To combine effects of bold and italic use 3 asterisks on both sides of the ***text***.
</span>  


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
Or using an asterisk * like so:
* line 1  
To indent the list add a space in front like this:
 * Line 2


### Blockquotes
<span class="left-justified">
Blockquotes are created by starting with a caret or greater than symbol followed by a space.
</span>
> Blockquote text

### Horizontal Rule
3 dashes will do the job.  

---  
 I'll keep adding to this as I start to use more formatting tricks.

 I have noticed that not all markdown is the same so you need to experiment.
