---
layout: post
section-type: post
title: Google Maps Quick Start
categories: ['web development']
tags: [ 'google maps', 'API', 'javascript']
---


#### Google Maps Quick Start

![Google Maps](/img/Google_maps_logo.png "Google Maps")

##### First Things First - Setting up your application
 

1. Sign-up in to your google account. If you really don't have one yet then go here to sign up for one... [Sign-Up for Google Account](https://accounts.google.com)    

2. Now once this is done you will need to register an application for using the Google API's needed for the app. Go here to do that... [Sign-Up for Google API](https://console.developers.google.com)
	A. Click 'Select a Project' and now click 'Create a Project' at the top right hand side of the screen.
	![Create a Project](/img/create_google_project.png "Create a Project")
	B. Give your project a name, choose whether to allow updates by email and then accept the licence aggreement. Click Create.  
3. For this app we'll be wanting to enable the following Google API's.  
	A. Google Maps Javascript API  
	B. Google Maps Road API  
	C. Google Static Maps API  
	D. Google Street View Image API  
	E. Google Maps Places API Web Service  
	F. Google Maps Geocoding API  
	G. Google Maps Directions API  
	H. Google Maps Distance Matrix API  
	I. Google Maps Geolocation API  
	J. Google Maps Elevation API  
	K. Google Maps Time Zone API  
4. Under 'Google Maps APIs' click each of the above APIs and click the enable button.  
5. Click'Credentials' on the left side of the window.  
	A. Select the option API Key.  This API Key identifies your project to check quotas and access.  
	B. Select the 'Browser Key' button.  
	C. Give your API Key a name and click 'Create'.  
	D. Select the 'Server Key' button, this is for making server side requests, and again name your key and click 'create'.  
	![Create API Keys](/img/APIKeys.png "Create API Keys")


You now have registered an application and set up and enabled access to all of the APIs your app will need access to.  

We are ready to move on to creating a starter html page displaying a map.  


##### Lets build out our start map







