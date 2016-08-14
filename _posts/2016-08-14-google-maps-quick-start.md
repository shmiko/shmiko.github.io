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

&nbsp;**1.** Sign-in to your google account.  
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
&nbsp;&nbsp;It is important that you also add in a referral url, this is a web page that will be making requests to use your API key, unless you specificy the url here it will be wide open for anyone to use should they get a copy of your API.  
&nbsp;&nbsp;By having a referral url you limit the requests to only those known hosts. As such when developing locally all you need to do here is add 'localhost:8080'. Save.    
![Referral](/img/referral.png "Referral")  
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
	
</body>
</html>  
```  


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
&nbsp;&nbsp;Now save the html page, if you are in a new project directoty then just call it index.html, otherwise call it whatever you wish.  
![Start Map Result](/img/start_map.png "Start Map Result")
&nbsp;&nbsp;Because this is front end development only you will need to be running a web server to actually run this website locally and make the API calls.  
&nbsp;&nbsp;If you try to run you page you should get an error loading the map as the file path is not an authorised host to make requests to the google map s API using your API key. Hence why we need to run a local web server to serve the page and which also was added as a url referral when setting up the API browser key.  
 
&nbsp;&nbsp;You can and should split out the above code so as you have a seperate CSS file as well as a separate JS file, but for simplicity sake I have included them within a single file.



### Lets quickly setup a web server to enable running locally.  

This very simple server is intended to be run whilst using a Mac, Python is installed by default with OS X and as such this server command will just work out of the box.  
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



### Lets add some locations and markers to the map

We will start by simply setting a variable to hold the coords for the location marker but later we will explore how to get the coordinates from an address or the current location of the device loading the page.  

&nbsp;**1.** Add a variable to hold an object containing lat and lng attributes.  


```javascript
	var opera_house = {lat: -33.856159, lng: 151.215256};
```  

&nbsp;**2.** Add a variable to hold the locations marker.  Specifying the position which is the coors previousley set, the map for which the marker is to appear and in addition to those 2 required attributes we will set a title which will show up on hover of the location on the map.  


```javascript
	var marker = new google.maps.Marker({
      position: opera_house,
      map: map,
      title: 'Sydney Opera House'
    });
```

&nbsp;Reload the map and you will now see a map marker showing based on the position you set.  
![Map Marker](/img/marker.png "Map Marker")  

### Lets add an Info Window popup when we click the marker


&nbsp;**1.** Start by setting a variable to hold the infoWindow. Include a content attribute with text which will display within the popup window.  
&nbsp;**2.** Assign the infoWindow to the marker previousley added via an addListener method.  


```javascript
  var infowindow = new google.maps.infoWindow({
    	content: 'The Sydney Opera House is a major tourist attraction on the harbour' + 
    	' with direct view of the Sydney Harbour Bridge'
    });
    marker.addListener('click', function(){
    	//arguments are for the destination map and the anchor point - if you do not use the marker variable you would specify a point.
    	infowindow.open(map, marker);
    });
```

![Info Window](/img/info_window.png "Info Window")  


### Multiple locations each showing a marker


&nbsp;**1.** Let remove our single marker variable and change it to an empty marker array.   
```javascript
  var markers = [];
```
&nbsp;**2.** Add an array of locations, each with a title and coords.   
These locations would be best served up from a database but for now we will hardcode them.   

```javascript
  	//locations array - usually these would be served up via a database
	var locations = [
		{title: 'Sydney Opera House', location: {lat: -33.856159, lng: 151.215256}},
		{title: 'Sydney Harbour Bridge', location: {lat: -33.8523,lng: 151.2108}},
		{title: 'Botanic Gardens', location: {lat: -33.8642,lng: 151.2166}},
		{title: 'The Rocks', location: {lat: -33.8599,lng: 151.2090}},
		{title: 'Glebe', location: {lat: -33.8798,lng: 151.1854}},
		{title: 'Balmain', location: {lat: -33.8589,lng: 151.1791}}
	];
```

&nbsp;**3.** Add a new Info Window method without content attribute which will be used within the loop.     

```javascript
  	var largeInfowindow = new google.maps.InfoWindow();
```

&nbsp;**4.** We will loop through the locations array to create markers for each.   

```javascript
  	// The following group uses the location array to create an array of markers on initialize.
    for (var i = 0; i < locations.length; i++) {
      // Get the position from the location array.
      var position = locations[i].location;
      var title = locations[i].title;
      // Create a marker per location, and put into markers array.
      var marker = new google.maps.Marker({
        map: map,
        position: position,
        title: title,
        animation: google.maps.Animation.DROP,
        id: i
      });
      // Push the marker to our array of markers.
      markers.push(marker);
      // Create an onclick event to open an infowindow at each marker.
      marker.addListener('click', function() {
        populateInfoWindow(this, largeInfowindow);
      });
      bounds.extend(markers[i].position);
    }
```

&nbsp;**5.** Create a function to populate the info window when a marker is clicked     

```javascript
  // This function populates the infowindow when the marker is clicked. We'll only allow
  // one infowindow which will open at the marker that is clicked, and populate based
  // on that markers position.
  function populateInfoWindow(marker, infowindow) {
    // Check to make sure the infowindow is not already opened on this marker.
    if (infowindow.marker != marker) {
      infowindow.marker = marker;
      infowindow.setContent('<div>' + marker.title + '</div>');
      infowindow.open(map, marker);
      // Make sure the marker property is cleared if the infowindow is closed.
      infowindow.addListener('closeclick',function(){
        infowindow.setMarker(null);
      });
    }
  }
```


&nbsp;**6.** Set the bounds of the map, bounds relate to the furthest points in the viewpoint.    

```javascript
  	var bounds =  new google.maps.LatLngBounds();

  	// Extend the boundaries of the map for each marker
    bounds.extend(markers[i].position);
```

&nbsp;**7.** Tell the map to fit within the bounds set.    

```javascript
  	map.fitBounds(bounds);
```


![Multiple Loctions](/img/multiple_locations.png "Multiple Loctions")  









