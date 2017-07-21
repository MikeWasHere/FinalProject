![brand image](../img/DiversiTech-logo.png)
# Diversitech Project
## Table of Contents

1. [Introduction](#introduction)
2. [Importing Assets](#assets)
3. [Responsive Design](#responsive)

<a name="introduction"></a>
## Introduction
OOhh DiversiTech. DiversiTech is a comapny that gives builders the supply they need to build aaall types of things. I was presented with this project and from the mockups I recieved I realized that the Mobile version to Desktop version was significantly different. Meaning it was going to be very interesting to make this website responsive all the way down to mobile. See, typically you would scale the site down and rearrange things to make elements fit better depending on the screen size. This was almost a whole different design all together. Usually when things like that happen you will make a whole different site like m.diversitech.com - In this section im going to talk about media queries and responsiver design. I am also going to talk about importing assets and how to make them responsive as well.

<a name="assets"></a>
## Importing Assets
So, importing assets. One of the most important, fundamental things in building a website is knowing what your assets are and where to place them. Fortunately there are many different ways to import assets into your site. 
### Images
One of which is adding an image. By adding an image we would call the image tag ``` <img src="image/file/name/imagefilename.jpg" alt="quick image file example"> ``` This will add any image given that the file path is correct. You can also import an image if being hosted from another site like so ```<img src="example.com/imagefilename.jpg" alt="quick image file example"> ``` or some hosting website will give you a direct link to the image so you can put it in your ```src=""``` attribute. The benefit of importing an asset from a hosted site is cutting the load time. If you have a big file loading within your site, chances are its going to take a long time for it load. However, if you were to have it hosted on another site and let them worry about the loading cause chances are they already got that problem figured out, the hosted image loading into your site will be a lot faster because all the heavy work is being handled by the hosting website. 
### Videos
Lets say you want to import some videos, you can do that by calling the video tag ```<video></video>``` But you will also need to add the video inside like so:
``` 
<video width="400" controls>
    <source src="mov_bbb.mp4" type="video/mp4">
    <source src="mov_bbb.ogg" type="video/ogg">
    Your browser does not support HTML5 video.
</video> ```
You would want to include mp4 files considering that most browsers load mp4 files, you would also have an .ogg file which mostly stores artist and track information as well as metadata. Run this and you're video should be showing.

<a name="responsive"></a>
## Responsive Design VS Mobile Site
Responsiveness is a really big thing. Like, really big. Making a website is only half of it. Making sure it is responsive is the other half. Some companies like to take different approaches when it comes to their mobile version of their site. The main two are Responsive design which makes the site fall into place depending on the size of the screen the elements on the page will change order to better situate itself. Then there is Mobile site which is a site strictly for mobile view, usually a site will have [m.facebok.com](m.facebook.com) for instance is the mobile version of Facebook. It senses if your using a mobile browser and it will show the mobile site instead of the regular. Which one should I use? it all depends. A huge platform like Facebook would benefit having a mobile version of their site because they would like to downsize their experience and not show so much / load so much like their desktop site. Therefor making a mobile version would be benefitial to them. Responsive would suit just about anything else out there. As long as your site isnt a HUGE platform with different styling choices and features you want to toggle between mobile and desktop, then responsiveness is for you. 
In order to make things responsive, Media Queries will be your best friend. ```CSS  @media only screen and (max-width: 500px) { styling goes here }``` This means that when the screen resolution hits 500px this styling inside will take place. There is also ```CSS  @media only screen and (min-width: 500px) { styling goes here }``` Which means any styling that falls below 500px, the styling will no longer take affect. And last but not least you can also use both of them in one like ```CSS  @media only screen (min-width: 400px) and (max-width: 500px) { styling goes here }``` which states that the styling will only take place when the screen are between 400px and 500px. Anything above 500px will not show and anything below 400px will not show.

**Responsive Media:**
So, when making things responsive, you would want to make sure the media goes with the flow of things as well. I cant tell you how many times this little piece of knowledge gets over looked in websites. There are many different ways on going about how to deal with media. Some site load in a different version of the resource depending on which media query it hits like so:
<p data-height="265" data-theme-id="0" data-slug-hash="Zygqvy" data-default-tab="html,result" data-user="MikeWasHere" data-embed-version="2" data-pen-title="Zygqvy" class="codepen">See the Pen <a href="https://codepen.io/MikeWasHere/pen/Zygqvy/">Zygqvy</a> by Michael Perez (<a href="https://codepen.io/MikeWasHere">@MikeWasHere</a>) on <a href="https://codepen.io">CodePen</a>.</p>
<script async src="https://production-assets.codepen.io/assets/embed/ei.js"></script>
This states that once the screen hits 500px I want the desktop picture to not show and show the mobile version of the picture.
Another way of making the resource responsive is by putting the img inside of a container and giving the container a set width with % instead of pixels.
```
HTML/CSS

<style>
.img-container {
    width: 50%;   <---- Giving the container a width of 50%, The picture will always be, no matter what size, 50% of its container.
}

.img-container > img {
    width: 100%;    <---- Making sure the image takes up 100% of the container that it is in.
}
</style>

<div class="img-container">
    <img id="responsive-img" src="exampleofresponsive.png" alt="responsive example" >
</div>

```
In this example the whole image is fluid, it will adjust itself when to exactly what you tell it, no matter what screen size.