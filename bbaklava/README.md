# Overview of what I did in the BBaklava Project
## Table of Contents

1. [Introduction](#introduction)
2. [Using Angular Routes](#angularRoutes)
3. [Using Models](#usingModels)
4. [Using Animation](#animation)

<a name="introduction"></a>
## Introduction

Hello and welcome to BBaklava project. In this project I worked on numerous things including, marketing plan and designing the whole brand in general - That is called Branding. I enjoyed this project very much. I always enjoyed designing and making things look nice and simple. I also enjoy making the UI for website very easy and intuitive to use. What I am going to focus on here is what libraries I used to make this project awesome. One of the Libraries i used for this project is called Angular.

In this Project I will talk about how I used Angular to make a E-commerce CMS on a small online store. I will talk about how I used Routes to render the specific HTML needed. I will talk about how Angular Modals were used to bind any form elements in the HTML and store into a variable that would be able to be used throughout the website. I will also touch upon, my personal favorite, CSS animations! how I used subtle animations to make the website more user friendly and give it a smoother field. I hope you guys enjoy this section, lets get to work.

<a name="angularRoutes"></a>
## Using Angular Routes

Alright, so if you dont know Angular and what angular does checkout [Thinksters](https://thinkster.io/a-better-way-to-learn-angularjs) Tutorial on it. It's pretty easy to follow along and it gives you basic knowloedge of what this javascript framework is at its core. So, jumping into Angular Routes, at its core what its used for is to switch out HTML with the desired content without reloading the whole page. This saves a lot of load time considering the fact that you dont have to load the whole page but only just the section you need. For example: Lets say when a user clicks on your nav bar you will only want the right section of your page to change. You dont want the whole page to reload, considering that the right section of the page is changing, nothing more. You would, In your index.html you would put ```HTML <div ng-view></div>``` <---- that will be the container in which your selected content will be rendered in. Now, in the Javascript file we have our structure on what content to call depending on the URL. 
```Javascript 
angular.module('appRoutes', []).config(['$routeProvider', '$locationProvider', function($routeProvider, $locationProvider) {

	$routeProvider

		// home content
		.when('/', {
			templateUrl: 'views/home.html',
			controller: 'MainController'
		})
        
        // Store content
		.when('/store', {
			templateUrl: 'views/geek.html',
			controller: 'GeekController'
		})
        
        // About content
		.when('/about', {
			templateUrl: 'views/nerd.html',
			controller: 'NerdController'	
		})
        
        //Ingredients content
		.when('/ingredients', {
			templateUrl: 'views/ingredients.html',
			controller: 'NerdController'
		})
        
        //Social content
		.when('/social', {
			templateUrl: 'views/social.html',
			controller: 'NerdController'	
		})
        
        // Contact content
		.when('/contact', {
			templateUrl: 'views/contact.html',
			controller: 'NerdController'	
		})
        
        // Master content
		.when('/master', {
			templateUrl: 'views/master.html',
			controller: 'NerdController'	
		});

	// $locationProvider.html5Mode(true);

}]);
```
As you can see, if the URL reads ```websitename.com/about``` then the About HTML will load in the ```HTML <div ng-view></div>``` and replace whats already in there with the about HTML template. Routes also lets you load in the controllers of your choosing with each template which i find pretty awesome.