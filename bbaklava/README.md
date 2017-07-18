![brand image](../img/bbaklava-new-logo.png)
# Overview of what I did in the BBaklava Project
## Table of Contents

1. [Introduction](#introduction)
2. [Using Angular Routes](#angularRoutes)
3. [Using Directives](#usingDirectives)
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

}]);
```
As you can see, if the URL reads ```websitename.com/about``` then the About HTML will load in the ```HTML <div ng-view></div>``` and replace whats already in there with the about HTML template. Only the content changes, not the page - and that my friends is the beauty of angular routes. P.S. Routes also lets you load in the controllers of your choosing with each template which I find pretty awesome.

<a name="usingDirectives"></a>
## Using Directives

Ahh, Angular Directives. I find Directives to be pretty freaking cool in angular and heres why. What directives are in a nutshell, they are your own personalized HTML tags that load what you want, where you want just by adding a tag to the HTML. Lets say you call a Directive ```HTML <rightsidebar></rightsidebar>``` <---- That tag right there will load the content you out in it, so lets take a look on how that looks. 
```Javascript

angular.module('sidebar', [])
.directive("rightsidebar", function() {
  return {
    restrict: "E",
    template: "<div>here is some right sidebar magic for ya.</div>"
  }
});

```
So might look complex but, very simple, let me explain. That part where it says ```Javascript .directive("rightsidebar", function() ``` the ("rightsidebar") is what dictates the name of the custom HTML ```HTML <rightsidebar></rightsidebar>```. In the Return section, there is a "template" and there you would put what you would want it to render. in this case it would render a div that would say "here is some right sidebar magic for ya.". Your problably wondering what the "restict: E" is used for. It is just saying that this will restrict this directive to Elements.

<a name="animation"></a>
## Using Animation

In this project I added some CSS Animation to the site to make it look more pleasing to the user. Even though the animations where subtle, they are enough to make the site look more organic and lively. For instance, when a user would click on a link to display different content, it would fade in or fade slide up instead of just popping right in. The wonderful thing that i like about the CSS animations is that it makes the site look and feel more smoother, depending on how you use it. In this project I used [Animate.css](https://animate.css) and [hover.css](https://hover.css) to give the site some spunk. over here I am using animate.css to make the content fadein in an upward direction when the content is called.
```
html

<div class="aboutBody animated fadeInUp"> <!-- animate.css is called here in parent element -->
	<h1>About Us</h1>

	<p>Picture a 23-year-old young woman carrying a baby in one hand and a tray of Baklava in the other. That was my Mother taking her boss one of her specialty pastries and that was me gazing at what I soon found out was my destiny. The name was created to honor our Grandmother, Berjuhi Bakalian. My Grandmother passed her recipes down to my Mother, who passed it down to me.</p>
</div>
 
<img src="http://i.imgur.com/RuwRkGK.jpg" alt="Christine Kutlu Picture" width="400" height="423" id="kutluPic" class="animated fadeInRight">

```

In this following example I am going to show you how we used Hover animation on the side bar. So basically what happends is when you hover over a side element, it will slightly grow. As you can see all I did was add the ```class="hvr-grow"``` and the animation will be set.
```
html

<div>
    <ul>
        <li><a href="#/"><img src="../img/home-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">Home</p></a></li>
        <li><a href="#/store"><img src="../img/store-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">Store</p></a></li>
        <li><a href="#/about"><img src="../img/about-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">About us</p></a></li>
        <li><a href="#/ingredients"><img src="../img/ingredients-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">Ingredients</p></a></li>
        <li><a href="#/social"><img src="../img/social-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">Social</p></a></li>
        <li><a href="#/contact"><img src="../img/contact-icon.svg" class="hvr-grow" width="36" height="36"><p class="show animated fadeIn">Contacts</p></a></li>
    </ul>
</div>
```
[Hover.css](https://hover.css) has a lot of different animations you can use, if you like animations I strongly recommend you check what they have, super easy to set up.