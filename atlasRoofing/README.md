![brand image](../img/atlas-logo.png)
# The PHP project - Atlas Roofing
## Table of Contents

1. [Introduction](#introduction)
2. [Understanding the CMS](#CMS)
3. [Including PHP Templates](#templates)
4. [MVC Frame work](#mvc)

<a name="introduction"></a>
## Introduction
Hello and welcome to the PHP section of my Portfolio. In this section I will be talking about how we bult a custom CMS with PHP basically being the core of it. I am also going to talk about how we rendered some of these templates using PHP. This project really showed me what PHP can do and how similar it CAN be to javascript, still a lot of differences but also a lot of similarities... even with Python now that I think about, but well talk about that in another section. Thank you for your time and as always I hope you find this to be as informative and helpful to your cause. Lets dive in.


<a name="CMS"></a>
## Understanding the CMS
The CMS for this company was set up with mySQL and PHP being the brindge between the database and the Frontend. How it worked is I would build a template for different pages. A product page will have this type of styling, A informational page would have this type of styling, and so on so forth. The Template itself was housed inside the mySQL database and how we referenced it is giving it an ID. If the page that we were calling had an ID of 5 which equaled to an informational page, then we would return the desired template with the desired content. The content was done through the custom built CMS. So you would go on there and lets say you wanted to create a new page, You would create a new page and in there you will select what type of page it would be. From there, depending on what you chose, anything you added would go to specific sections of the page. This was done with PHP and a lot of "if statements" to make sure the styling wouldnt get compromised if you left something out.


<a name="templates"></a>
## Including PHP Templates
One of the great things of PHP is the ability to include certain sections on a page instead of something as a whole. Makking things more granular is good when you want to isolate and just work on one part of a site and not having to worry about searching for that section in one big file, instead everything is broken up to different sections. In PHP, If you wanted to add a footer, you would do ```php <?php include 'footer.php';?> ``` on the bottom of the file and it would render that "footer.php" file into the main file. Doing this way and seperating your files indivisually will save you a headache and will make it easier to debug things if something were to go wrong. Heres and example: This is the header portion
```
php

<!-- This is the Header portion -->
<html>
	<header>
		<link rel="stylesheet" type="text/css" href="css/bootstrap.min.css">
		<link rel="stylesheet" type="text/css" href="css/style.css">    
	    <link href='http://fonts.googleapis.com/css?family=Voltaire' rel='stylesheet' type='text/css'>
	</header>
	
	<style>
	.modal-backdrop{
		z-index: 0;
	}
	
	.modal-footer{
	padding-bottom: 0;
	}
	
	
	</style>
	
	<body>
<div class="navbar navbar-fixed-top alt" data-spy="affix" data-offset-top="1000">
  <div class="container">
    <div class="navbar-header">
      <a href="?controller=home&action=home" class="navbar-brand">Home</a>
      <a class="navbar-toggle" data-toggle="collapse" data-target=".navbar-collapse">
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
        <span class="icon-bar"></span>
      </a>
    </div>
    <div class="navbar-collapse collapse" id="navbar">
      <ul class="nav navbar-nav">
        <li><a href="#" data-toggle="modal" data-target="#myModal2">Add User</a></li>
        <li><a href="?controller=home&action=uploadForm" >Upload Form</a></li>
        <li><a data-toggle="modal" data-target="#myModal">Login</a></li>
      </ul>
    </div>
   </div>
</div>
```

now this is the body portion:
```
php

<div class="header alt vert">
  <div class="container">
    
    <h1>CapitalCity</h1>
      <p class="lead">Starter Template for Bootstrap 3</p>
  </div>
</div>
```

Last but not least heres the Footer:
```
php

<footer>
  <div class="container">
    <div class="row">
      <div class="col-md-6 col-md-offset-3 text-center">
        <ul class="list-inline">
          <li><i class="icon-facebook icon-2x"></i></li>
          <li><i class="icon-twitter icon-2x"></i></li>
          <li><i class="icon-google-plus icon-2x"></i></li>
          <li><i class="icon-pinterest icon-2x"></i></li>
        </ul>
        <hr>
        <p>Built with <i class="icon-heart-empty"></i> at <a href="http://www.bootply.com">Bootply</a>.<br>Company ©2014</p>
      </div>
    </div>
  </div>
</footer>

<ul class="nav pull-right scroll-down">
  <li><a href="#" title="Scroll down"><i class="icon-chevron-down icon-3x"></i></a></li>
</ul>
<ul class="nav pull-right scroll-top">
  <li><a href="#" title="Scroll to top"><i class="icon-chevron-up icon-3x"></i></a></li>
</ul>
	</body>
	
	<!-- jQuery (necessary for Bootstrap's JavaScript plugins) -->
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.0/jquery.min.js"></script>
    <!-- Include all compiled plugins (below), or include individual files as needed -->
    <script src="js/bootstrap.min.js"></script>
    
   
 <script>
    $('.popoverbutton').popover()
    $('#myModal').modal(options)
 </script>
	
 <script type="text/javascript" src= "js/main.js"></script>

</html>
```
So now that we have all those pieces, how do we put them together to display in one page? heres how, Includes baby. in your main file all you have to do is:
```
php

<?php 
include 'header.php';
include 'body.php';
include 'footer.php';
?>
```
And thats it. Its in there. Remember, the beauty in this is so everything is broken up in a way that its easier to manage. Hope this helps! 

<a name="mvc"></a>
## MVC Frame work
You may be familiar with the MVC framework. From my undertanding every language has the ability to use this type of architecture in there system. If you don't know let me give you a quick rundown on what it is. M.V.C. Stands for Model View Controller and what it does is a simple way of keeping things in order. Think of it like watching TV: Model is the cable box that has all the channels(data) that you need. Views just displays what you want like a TV(your templates). And Controller is your is what connects the cable box(data) and the TV(your templates) and tells your Model "I want this" your Model then sends this to your controller and your controller says "Heres the data -  this data goes with this Template" and boom. Everything shows. Thats MVC in a nut shell. So let me show you how it would look. This is the Model:
```
php

This is a Model

<?

class login{    
    // A function that checks the user, if user is true, return all the user information
	public function checkuser($user){
		$dbh = new PDO("mysql:host=localhost;dbname=SSL;port=8889","root","root");     //<--- you would never pass the password like this but for the sake of the example
		
		$sql = "select username, password from users where 
						username = :username and password = :password"; 
						
		$st = $dbh->prepare($sql);
		
		$st->execute(array(":username"=>$user["username"],
							":password"=>md5($user["password"])));
		
		return $st->fetchAll();
	
		if($st->fetchAll()){
			return 1;
		}else{
			return 0;
		}
	
	}
	
		}
?>
```
This is the View (Rule of thumb: you usually want to make your view file a php file as well for this to work because in PHP you can still write regular HTML without any problems):
```
php

<?
		<div id="results">
		<a href="?controller=home&action=uploadForm" >Update Database</a>
		<a href="?controller=home&action=inJSON">Check Weather</a>
		<ul id="mid">';
            <li class='exposed'><b><p class='exp'>UserName: </p></b>".$_POST["username"]</li></br>";
            <li class='exposed'><b><p class='exp'>Password: </p></b>".$_POST["password"]</li></br>";
            <li class='exposed'><b><p class='exp'>State: </p></b>".$_POST["state"]</li></br>";
        </ul>
        <a id='logouut' class='btn btn-default btn-lg' href='?controller=home&action=Logout'>Logout</a>
?>
```
And here we have your Controller: 
```
php

<?php 
// First we need to include all these models
include 'model/view.php';
include 'model/file.php';
include 'model/login.php'; 
include 'model/users.php'; 

//Then we insantiate these models
$viewmodel = new view();
$filemodel = new file();
$loginmodel = new login();
$usersmodel = new users();

// Followed by some IF statements

if($_GET["action"]=="home"){
    $data = $usersmodel->getUsers();
    $viewmodel->getView("views/header.php");
    $viewmodel->getView("views/body.php",$data); // load the body view
    $viewmodel->getView("views/footer.php");
        
}else if($_GET["action"]=="addUser"){
    $data = $usersmodel->addUser($_POST["username"],$_POST["password"]);
    $data = $usersmodel->getUsers();
    $viewmodel->getView("views/header.php");
    $viewmodel->getView("views/results.php",$data); // load the results view
    $viewmodel->getView("views/footer.php");

}
?>
```

So as you can see here the controller controls what view to show depending on what the user does. Here as you can see if the user is "home" then it will render the "body.php" view, If the user is in the "addUser" then it will switch out the body and load in the "results.php" instead.
There some pretty basic MVC structure. Hope this helps!