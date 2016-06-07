---
layout: post
section-type: post
title: Google Maps, Calendar, Fusion Tables and App Scripts
categories: ['web_development']
tags: [ 'google_maps','google_calendar','google_app_script']
---


#### How to use Google Calendar Events on Google Maps and using App Scripts to work some magic  

I had an issue where I was pulling in some Google Calendar events and plotting them to a Google Map.  

What I wanted though was to use event categories to sperate out certain events. 

The solution I came up with was due to the fact that the Version 3 API did not allow you to access the event colors so there was no other way to categorise events.
So anyway what i end up doing was a 2 part solution. 

The first part was to add to the event description some specific syntax that could be interpreted by code to add some seperation and apply a category when reading the data.

Doing this via the API was not ideal as it was quite slow due to the need for geocoding at the same time as reading via the API.  

What i decided to do next was to write a Google App Script to read the data via the Calendar API and save the data to a google sheet.  
The using fusion tables I was able to geocode much quicker, but there are quota limits which sometimes offset the benefit especially if I was to reprocess whilst testing.  
After the fusion table was finished processing the data I was then able to bring the data into my JS script and could use the categories created using the app script code.  

Now it was simply a matter of using a specific map icon for each relevent category.

This turned out to be a much better solution than what I originally had planned in using the event colors.  

This was done nearly 2 years ago and still it is my understanding that there is no way to use event colors.  

I have not seen any other calendar mapping applicatiosn to use categories so I have nothing to compare my solution with.

 I'll post the app script I wrote to produce the fusion tables soon. Witht he JS solution you need to have an API key for fusion tables, calendar and maps.  


 The working maps to show this can be seen here [CalMapIt - Holiday Calendar Map](http://calmapit.com/calmapit.html) 
 PS - There is some really big images which I have yet to optimise so it will take a while to load. This was just a proof of concept though and not a production app.   