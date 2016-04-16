---
layout: post
section-type: post
title: AngularJS Wikipedia Search
categories: ['programming']
tags: [ 'angularjs','wikipedia']
---


## Adding a Wikipedia Voice Enabled Search to your AngularJS App!  

What I like most about AngularJS is how modular it is. Yu can very easily add new functionality to your site withut too much heavy lifting.
I'm going to list the steps involved in adding a Wikipedia Search to your AngularJS App.
We're using Angular 1.6 but I will soon upoad the same functionality using AngularJS 2.
It is assumed that you are pretty comfortable with Angular and understand the various components and how they interact with each other.

Ready..Let's Go.

We will be dealing with Front End only and as such our directory structure will be structured like this:  
The top level is you App Name, then you will have the following directories client, server, bower_components, node_modules and hopefully a test directory.  
Within client I have an app and assets.
The app directory holds all the various parts of the client side functionality including the main pages which tie the AngularJS app together and all the asociated modules.  
This App structure is based on the Angular [Style Guide](http://github.com/johnpapa/angular-styleguide) by John Papa http://github.com/johnpapa/angular-styleguide.  

It looks like this:
![Image of Wikipedia Directory Structure](../../../../img/wiki_app_layout.jpg)


First you will need to setup the angular app.modules.js file with the injected wikipedia module.  

```javascript
(function () { 
"use strict";
    var app = angular.module('myApp', ['ngRoute','wikipedia']);
}());
```

Now we will also provision the route whihc will direct the user to the wikipedia page.  

```javascript
(function () {
"use strict";

angular.module('myApp')
    .config(['$stateProvider','$httpProvider','$routeProvider','$urlRouterProvider', function ($stateProvider,$httpProvider,$routeProvider,$urlRouterProvider) {
        $urlRouterProvider.otherwise('/intro');

        //Using Route Providor
    	//List all routes as an array and loop
        var routes = [
        {
           url: '/wikipedia',
           config: {
               controller: 'wikipediaController',
               templateUrl: '/app/wikipedia/wikipedia.html'
           }
        }];

	    //loop through routes array
	    routes.forEach(function (route) {
	        $routeProvider.when(route.url, route.config);
	    });

	    //default route if nothing specified
	    $routeProvider.otherwise({ redirectTo: '/index.html' });

	    //Using Route State Providor
	    $stateProvider
            .state('wikipedia',{
                url:'/wikipedia',
                templateUrl : 'app/wikipedia/wikipedia.html',
                controller  : 'wikipediaController'
            });

    }]);

})();
```

Now we can start to look at the wikipedia module.  
This module is found on github but it was lacking attribution details hence why there is none.
This module is quite complete and works with voice commands.
You do not need an API key either.

```javascript
  var app = angular.module('Wikipedia', []);

  	//create the service to get data from API and initiate a random search
    app.factory('GetSearch', function($http) {
      var wiki = {};
      wiki.jsonp = '&callback=JSON_CALLBACK';
      wiki.getWiki = function(term) {
        var endPoint = 'https://en.wikipedia.org/w/api.php?format=json&action=query&generator=search&gsrnamespace=0&gsrlimit=15&prop=pageimages|extracts&pilimit=max&exintro&explaintext&exsentences=1&exlimit=max&gsrsearch=';
        return $http.jsonp(endPoint + term + wiki.jsonp);
      };

      wiki.getRandom = function() {
        var endPoint = 'http://randomword.setgetgo.com/get.php';
        return $http.jsonp(endPoint + "?callback=JSON_CALLBACK");
      };

      return wiki;
    });

  app.controller('wikipediaController', function(GetSearch, $scope) { /*Model data bank*/

  	//set variables
  	$scope.MainData = {};
    $scope.MainData.results = [];
    $scope.MainData.listen = null;
    $scope.MainData.search = function(term) {
      GetResults($('input.dirty').val());
    };

    // on random search call this
    $scope.MainData.Random = function(term) {
      RandomSearch(term);
    };

    //When Mic icon is clicked
    $scope.MainData.Speech = function(url) {
      StartSpeech();
    };

    // GET  SEARCH 'from wikipedia'
    function GetResults(term) {
      $('input.dirty').val(''); //clear input field
      GetSearch.getWiki(term).success(function(data) {
        Render(data);
      });
    }

    // GET RANDOM WORD
    function RandomSearch() {
      GetSearch.getRandom().success(function(data) {
        GetResults(data.Word); // search with random word
        $scope.MainData.val = data.Word;
      });
    }

    //Render Data
    function Render(data) {
      var url = 'http://en.wikipedia.org/?curid=';
      var Value = data.query.pages;
      $scope.MainData.results = []; // reset data
      for (var key in Value) {
        var obj = {};
        var insideValue = Value[key];
        obj.title = insideValue.title;
        obj.text = insideValue.extract;
        obj.url = url + insideValue.pageid;
        $scope.MainData.results.push(obj);
      }
    }

    /*auto completion*/
    $(document).ready(function() {
      $(".dirty").autocomplete({

        source: function(request, response) {
          $.ajax({
            url: "https://en.wikipedia.org/w/api.php",
            dataType: "jsonp",
            data: {
              'action': "opensearch",
              'format': "json",
              'search': request.term,
              'gsrlimit': 8
            },
            success: function(data) {
              response(data[1]);
              $scope.$apply();
            }
          });
        },
        select: function(event, ui) {
          $scope.MainData.search();
        }

      });

    });

    //notification sounds
    var findSound = "http://oringz.com/ringtone/just-like-magic/sounds-948-just-like-magic/?download"
    var wikiSound = 'http://oringz.com/ringtone/gets-in-the-way/sounds-874-gets-in-the-way/?download';
    var findAudio = new Audio(findSound);
    var wikiAudio = new Audio(wikiSound);

    // Voice search
    function StartSpeech() {
      $('input.dirty').val(''); //clear input field
      if ($scope.MainData.listen) {
        $scope.MainData.listen = null;
        animate();
        return annyang.abort();
      } else {
        animate();
        $scope.MainData.listen = true;
        var commands = {
          'find *term': function(term) {
            GetResults(term);
            $scope.MainData.listen = null;
            $scope.MainData.val = term;
            animate();
            findAudio.play();
            return annyang.abort();

          },
          'wikipedia': function(term) {
            wikiAudio.play();
            //change placeholder
            $("input.dirty").attr("placeholder", 'Say "Find" + any Word').val("")
          },

        };

        annyang.addCommands(commands);
        annyang.start();
      }
    }

    // change placeholder and toggle some classes
    function animate() {
      $("input.dirty").attr("placeholder", 'Say "Wikipidia"').val("")
      $('.icon').toggleClass('listen');
    }

  });
```
Now just check the css is to your liking.

```css

.form-control-feedback{
  cursor:pointer;  
  color:#000000;
}

.card{
  cursor:pointer;
}

.card:hover{
    box-shadow: 1px 1px #000000;
}

.mic_span a{
  display:block;
  margin:10px;
}

.jumbotron{
  padding: 0.5em 0.6em;
}
.listen{
  color:red;
}
.tweet{
  display:inline-block;
}
.fa-twitter-square{
	color:#000000;
}

```

And lastly the html page.  

```html
<div class="jumbotron text-center" md-theme="aqua">
    <h2>Wikipidia Voice Seach </h2>
      
    <div class="text-center ">
 
      <form class="form-inline" ng-submit="MainData.search(MainData.val)">
       <div class="form-group has-feedback">
         
          <input type='text' class="form-control dirty ui-autocomplete-input" autocomplete="off" placeholder='Search' ng-model="MainData.val" required/>
          <span class='mic_span'><a class="fa fa-microphone fa-lg form-control-feedback icon" style="pointer-events: auto;" ng-click="MainData.Speech()"></a>
          </span>
        </div>
        
        <button type="button" class="btn btn-info autoplay" ng-click="MainData.Random()">Random Search</button>
        
     </form>
    </div>

  </div>

  <div class="container">
    <div>
      
    </div>
    <div ng-repeat="term in MainData.results">
        <md-card>
        <md-card-content class="card" style="color: #FFF; padding:5px;"> 
        <h2 class="md-title">{{term.title}} <a ng-href="{{term.url}}" target="_blank"><i class="fa fa-external-link-square"></i></a></h2>
        <p>{{term.text}}</p>
    </div>
  </div>
```
The last final step is to include the wikipedia css and js file in your index.hlml.

The result will look something like this if you choose to search for **javascript**.  
![Image of Wikipedia Result](../../../../img/wiki_results.jpg)  


This will take about 15 minutes to implement and adds some great functionality.

Boom!....


