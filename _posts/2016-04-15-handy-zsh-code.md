---
layout: post
section-type: post
title: Handly Little ZShell Time Savers
categories: ['zshell']
tags: [ 'zshell','time_savers']
---


## Handy Little Terminal Time Savers!  

When I first started to use ZSH - Zshell with iTerm on Mac I noticed that many common comands were far too repetitive.  
I'm used to the DRY ( Don't Repeat Yourself ) principle and figured out that you can add some scripting to your  bash or shell file to automate many common tasks.  
I use the file .zshrc to control my terminal commands, but you might be using the bash shell where things are different but still possible.   
The file should be located in the bin directory.  
You can get to this file using the terminal starting in your user root directory, then type open .zshrc.   
This will open the file in the system default text editor which on Mac will likely be TextEdit.  
If the file doesn't exist create it.  

First things first, we need to pretty things up a bit, add some color, and some line feedback.  
- **autoload -U colors && colors** will expose the system colors.  
- **PROMPT=" $fg[red]%n** will show the current user name as Red text.  
- **$reset_color** will reset the color from red and beside that *@* will show an ampersand.  
- **$fg[cyan]%m$fg[yellow] %~** shows current user in Cyan and the working directory in Yellow.  
- **$fg[green]>$reset_color** will set a Green prompt as a greater than symbol where you type commands and finally reset the color.  
- **RPROMPT="%T"** will place on the right hand side of the screen the time that a line was written, this is very useful when navigating throught he terminal looking at previous steps.  

```javascript
autoload -U colors && colors

PROMPT=" 
$fg[red]%n$reset_color@$fg[cyan]%m$fg[yellow] %~
$fg[green]>$reset_color "

RPROMPT="%T"
``` 
This is how is looks:
![Image of Terminal](../../../../img/term1.jpg)


Next was to allow running a local server with just 1 word.  
I needed a way to quickly get a localhost running for many front end projects that had not yet progressed to getting a back end.  
Solution was to run up a Node server or a Python server.   
I chose to do both as quite often I would need to run up multiple localhosts.  
Here is some code you can add to give this functional time saver.  
These are 2 very simple functions that will be run by just typing the function names, either **server** or **nserver** 
You will notice I use different PORTS so as to allow for 2 localhosts.   

```javascript
//creates a python server on port 8000
function server (){
	if [ $1 ]
	then
		local port="$1"
	else
		local port="8000"
	fi
	open "http://localhost:$port" && python -m SimpleHTTPServer "$port"
}
 
//creates a node server on port 8080
function nserver (){
	http-server
}
```   

Another common task is working with git, either github or heroku.  
These are again very simple commands that just save you typing the whole command.  
I dont use one for git commit as the comment needs to be set every time and these command will initiate hitting the return key.  
You simply type the function name.
So to add all files to your git repo, assuning you are in the correct directory just type *gita*.
Likewise to push to github just type * gitpo*.

```
//simply types git add.
function gita (){
	git add .
}

//simply types git push origin master
function gitpo (){
	git push origin master
}

//simply types git push heroku master
function gitph (){
	git push heroku master
}

```

I have also written functions to set my web development working directory, starting up a MongoDB server and also to connect to an AWS EC2 instance.

There will no doubt be better ways to do these things but these work well for me. Search the net and you will find many help topics to help you further customise you shell.
A very common tool is the OH MY ZSHELL, this has many features including themes to make these type of changes much easier.


