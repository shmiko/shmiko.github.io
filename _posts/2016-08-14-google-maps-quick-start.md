---
layout: post
section-type: post
title: Google Maps Quick Start
categories: ['web development']
tags: [ 'google maps', 'API', 'javascript']
---


#### Google Maps Quick Start

![Google Maps](/img/Google_maps_logo.png "Google Maps")

### First Things First - Setting up your application

&nbsp;**1.** Sign-up in to your google account.  
&nbsp;&nbsp;If you really don't have one yet then go here to sign up for one... [Sign-Up for Google Account](https://accounts.google.com)    

&nbsp;**2.** Now once this is done you will need to register an application for using the Google API's needed for the app. Go here to do that... [Sign-Up for Google API](https://console.developers.google.com)  
&nbsp;&nbsp;Click 'Select a Project' and now click 'Create a Project' at the top right hand side of the screen.  
![Create a Project](/img/create_google_project.png "Create a Project")  
&nbsp;&nbsp;Give your project a name, choose whether to allow updates by email and then accept the licence aggreement. Click Create.  

&nbsp;**3.** For this app we'll be wanting to enable the following Google API's.  
&nbsp;&nbsp;&nbsp;Google Maps Javascript API  
&nbsp;&nbsp;&nbsp;Google Maps Road API  
&nbsp;&nbsp;&nbsp;Google Static Maps API  
&nbsp;&nbsp;&nbsp;Google Street View Image API  
&nbsp;&nbsp;&nbsp;Google Maps Places API Web Service  
&nbsp;&nbsp;&nbsp;Google Maps Geocoding API  
&nbsp;&nbsp;&nbsp;Google Maps Directions API  
&nbsp;&nbsp;&nbsp;Google Maps Distance Matrix API  
&nbsp;&nbsp;&nbsp;Google Maps Geolocation API  
&nbsp;&nbsp;&nbsp;Google Maps Elevation API  
&nbsp;&nbsp;&nbsp;Google Maps Time Zone API  
&nbsp;&nbsp;Under 'Google Maps APIs' click each of the above APIs and click the enable button.  

&nbsp;**4.** Click'Credentials' on the left side of the window.  
![Create API Keys](/img/APIKeys.png "Create API Keys")
&nbsp;&nbsp;Select the option API Key.  This API Key identifies your project to check quotas and access.  
&nbsp;&nbsp;Select the 'Browser Key' button.  
&nbsp;&nbsp;Give your API Key a name and click 'Create'.  
&nbsp;&nbsp;Select the 'Server Key' button, this is for making server side requests, and again name your key and click 'create'.  

You now have registered an application and set up and enabled access to all of the APIs your app will need access to.  

We are ready to move on to creating a starter html page displaying a map.  


### Lets build out our start map

We are using the latest version 3.24 of the Google javascript API.  
&nbsp;**1.** Setup the basic html page.  
```html
<!DOCTYPE html>
<html>
<head>
	<title>Start Map</title>
</head>
<body>
	
</body>
</html>
```
&nbsp;&nbsp;Add the following CSS to apply a little bit of formatting and sizing for the map.  
<!DOCTYPE html>
<html>
<head>
	<title>Start Map</title>
	<style>
		html,body{
			font-family: Arial, sans-serif;
			height: 100%;
			margin: 0;
			padding: 0;
		}

		#map{
			height: 100%;
		}
	</style>
</head>
<body>
	
</body>
</html>  
&nbsp;&nbsp;Add a DIV tag with an ID of map.  
&nbsp;&nbsp;Next add the following script to pull in the google map API resource.  
```html
<!DOCTYPE html>
<html>
<head>
	<title>Start Map</title>
	<style>
		html,body{
			font-family: Arial, sans-serif;
			height: 100%;
			margin: 0;
			padding: 0;
		}

		#map{
			height: 100%;
		}
	</style>
</head>
<body>
	<div id="map"></div>
    <script>
      var map;
      function initMap() {
        // This constructor creates a new google map - center and zoom are the only default arguments required.
        map = new google.maps.Map(document.getElementById('map'), {
          center: {lat: -33.869831, lng: 151.196872 },
		  zoom: 8
        });
      }
    </script>
    <script async defer
        src="https://maps.googleapis.com/maps/api/js?key=API_KEY&v=3&callback=initMap">
    </script>
</body>
</html> 
``` 
&nbsp;&nbsp;&nbsp;&nbsp;You will need to replace API_KEY with the browser API key you set up earlier.  
&nbsp;&nbsp;Now save the html page, if you are in a new project directoty then just call it index.html.
&nbsp;**4.** Click'Credentials' on the left side of the window.  
![Start Map Result](/img/start_map.png "Start Map Result")
&nbsp;&nbsp;Because this is front end development only you will need to be running a web server to actually run this website locally and make the API calls. 

 

### Lets quickly setup a web server to eable running locally.  

This very simple server is intended to be run using a Mac as Python is installed by default with OS X and as such this server command will just work.  
&nbsp;&nbsp;Go to the command line and change to the current working directory and run the following to open your default browser to display the page just created which should now show a basic google map.  
```javascript
open "http://localhost:8080" && python -m SimpleHTTPServer 8080
```


**Windows users**  
Go to Google and search for WAMP.  
Open the page and install this package.  
This will enable the same functionality in a sigle package install.    
Alternatively it is probably easier to run a node js server if you are comfortable doing so, but if you are not familiar with using the command line then stick to WAMP.  
WAMP however will install more than just a web server and as such you will get a full blown back end environment ready to run sites with an Apache Server, MySQL Database and suitable for running PHP in addition to other code based pages.  















