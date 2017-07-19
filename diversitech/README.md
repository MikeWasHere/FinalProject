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
## Responsive Design

