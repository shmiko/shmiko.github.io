---
layout: post
section-type: post
title: AngularJS Performance
categories: ['programming']
tags: [ 'angularjs','wikipedia']
---


#### AngulatJS Performance.  

Cache data whenever possible  
Use native JavaScript slower functions. Of use Lodash.   
Using ng-repeat will add to poor performance but it must be weighed. Also using infinite scrolling will help with the use of track by.   
Use $watchCollection instead of $watch (with a 3rd parameter) - this will force Angular to check first layer only.    
Avoid repeated filters|pipes if possible especially with one time binding. 
Try ng-if instead of ng-show but wiegh the decision if you use specific toggles.  
Try not to use $watchers due to dirty checking, small apps will be ok though    
Batarang will help you benchmark your $watchers.   
