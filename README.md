## Website Performance Optimization portfolio project

To Run the Project:
  1.  Right click on index.html and select open with Google Chrome.
  2.  Once running, click on any of the 3 top links to learn more about Cam.
  3.  Click on the bottom link to order a Pizza from Cam's pizzaria.


Part 1: Optimize PageSpeed Insights score for index.html

I optimised the index.html by :

1.  Minify CSS, HTML and JavaScript
2.  Eliminate render-blocking JavaScript and CSS in above-the-fold content
3.  Using "async" for non -render blocking javascript
4.  inlining CSS
5.  put uncompressed html file in folder called PRECOMPFILES
6.  put uncompressed css file in the css folder by original name, but compressed file and chaneg the entire file to inline css in the index.html file
7.  edited pizzeria.jpg to use less resources

Set up test by:
1.  Open a tunnel to the internet using port 8080 using ngrok and running command ngrok 8080.
2.  Open a CygwinTermianl and set pot to 8080 using the following command:
    python -m SimpleHTTPServer 8080

Once port setand ngrok URL provided, run page speed insights on the index.html file.
Page speed insights reveals:  	mobile speed of 96/100 with a 100% user experirnce
								Desktop speed of 97/100




Part 2: Optimize Frames per Second in pizza.html

Ensuring a consistent frame rate of 60fps

1.  reducing the number of pizzas created to 20 (line 537)
2.  using translate instead of basic left positioing (line 521): item[i].style.left = 'translateX(' + (100*phase) + 'px)'; 
3.  var items = document.getElementsByClassName('mover'); // Cache items changed to use getElementsByClassName as suggested line 510
4.  var len = items.length; // Cache length line 511
5.  moving the calculation of a big number ouside the loop (line 515) : var number=document.body.scrollTop / 1250;
6. made the following changes to the changePizzaSizes function
	cached the length so that the CRP pathint called everytime through the loop to calulate the legth of the array (line 453)
	using console.log I found that the values being calculated for DX and newwidth were the same no matter what vailue was in i.
	I decided to calculate then one at start of function with the 0 value because the difference between subscripts was neglegable.
	declared the new i variable outside the for loop on line 456
	moved the var for dx and new width outside the for loop, lines 457, 458.


function changePizzaSizes(size) {
    var len = document.querySelectorAll(".randomPizzaContainer").length; // cache length
// using console.log I found that the values being calculated for DX and newwidth were the same no matter what vailue was in i.
// I decided to calculate then one at start of function with the 0 value because the difference between subscripts was neglegable.
    var i = 0;
    var dx = determineDx(document.querySelectorAll(".randomPizzaContainer")[i], size);
    var newwidth = (document.querySelectorAll(".randomPizzaContainer")[i].offsetWidth + dx) + 'px';

    for (var i = 0; i < len; i++) {  
      document.querySelectorAll(".randomPizzaContainer")[i].style.width = newwidth;
    }
  }

  changePizzaSizes(size);




Resources: 1. http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/
           2. http://stackoverflow.com/questions/16987787/css3-translate-vs-translatex
           3. fork grunt-pagespeed-ngrok-sample from github
In addition to the above website I read many websites pertaining to NGROK and how to use github.IO in order to accomplplish the first part of the project.
I did get github.io to work, but the problem I had with it was that I had to continuously post me code change to my github.io project in order to see my changes reflect on the website.

I decided that this was not the best way to accomplsih this task, so I deceided to figure out how to get ngrok to work.

I did have many issues with this, but I finally got it to work using Cygwin, so this is the program I used to get the Linux like environemnt working on my Wndows 8 machine.

It would have been very helpful if the lecrture would have mentioned that the website we were goign to run on our project from our local machine had to actually run onllne.

If I would have known this up front, I could have done the reserach before I took the lecture and managed my time differently.  As it is, I am tuning this project in at the last minute.  
I feel confident that I was able to accomplish all that I needed, but it just would have made my life easier to have know this up front.