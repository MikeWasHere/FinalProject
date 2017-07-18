![brand image](../img/atlas-logo.png)
# Atlas Roofing - The PHP project
## Table of Contents

1. [Introduction](#introduction)
2. [Understanding the CMS](#CMS)
3. [Including PHP Templates](#templates)

<a name="introduction"></a>
## Introduction
Hello and welcome to the PHP section of my Portfolio. In this section I will be talking about how we bult a custom CMS with PHP basically being the core of it. I am also going to talk about how we rendered some of these templates using PHP. This project really showed me what PHP can do and how similar it CAN be to javascript, still a lot of differences but also a lot of similarities... even with Python now that I think about, but well talk about that in another section. Thank you for your time and as always I hope you find this to be as informative and helpful to your cause. Lets dive in.


<a name="CMS"></a>
## Understanding the CMS
The CMS for this company was set up with mySQL and PHP being the brindge between the database and the Frontend. How it worked is I would build a template for different pages. A product page will have this type of styling, A informational page would have this type of styling, and so on so forth. The Template itself was housed inside the mySQL database and how we referenced it is giving it an ID. If the page that we were calling had an ID of 5 which equaled to an informational page, then we would return the desired template with the desired content. The content was done through the custom built CMS. So you would go on there and lets say you wanted to create a new page, You would create a new page and in there you will select what type of page it would be. From there, depending on what you chose, anything you added would go to specific sections of the page. This was done with PHP and a lot of "if statements" to make sure the styling wouldnt get compromised if you left something out.


<a name="templates"></a>
## Including PHP Templates
One of the great things of PHP is the ability to include certain sections on a page instead of something as a whole. Makking things more granular is good when you want to isolate and just work on one part of a site and not having to worry about searching for that section in one big file, instead everything is broken up to different sections. In PHP, If you wanted to add a footer, you would do ```php <?php include 'footer.php';?> ``` on the bottom of the file and it would render that "footer.php" file into the main file. Doing this way and seperating your files indivisually will save you a headache and will make it easier to debug things if something were to go wrong.