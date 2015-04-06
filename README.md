## Website Performance Optimization portfolio project

Part 1: Optimize PageSpeed Insights score for index.html

I optimised the index.html by :

1.  Minify CSS, HTML and JavaScript
2.  Eliminate render-blocking JavaScript and CSS in above-the-fold content
3.  Using "async" for non -render blocking javascript
4.  inlining CSS

Part 2: Optimize Frames per Second in pizza.html

Ensuring a consistent frame rate of 60fps

1.  reducing the number of pizzas created to 20 (line 532)
2.  using translate instead of basic left positioing (line 512): item[i].style.left = 'translateX(' + (100*phase) + 'px)';
3.  moving the calculation of a big number ouside the loop (line 508/510) : var number=document.body.scrollTop / 1250;
Resources: 1. http://www.paulirish.com/2012/why-moving-elements-with-translate-is-better-than-posabs-topleft/
           2. http://stackoverflow.com/questions/16987787/css3-translate-vs-translatex

In addition to the above website I read many websites pertaining to NGROK and how to use github.IO in order to accomplplish the first part of the project.
I did get github.io to work, but the problem I had with it was that I had to continuously post me code change to my github.io project in order to see my changes reflect on the website.

I decided that this was not the best way to accomplsih this task, so I deceided to figure out how to get ngrok to work.

I did have many issues with this, but I finally got it to work using Cygwin, so this is the program I used to get the Linux like environemnt working on my Wndows 8 machine.

It would have been very helpful if the lecrture would have mentioned that the website we were goign to run on our project from our local machine had to actually run onllne.

If I would have known this up front, I could have done the reserach before I took the lecture and managed my time differently.  As it is, I am tuning this project in at the last minute.  
I feel confident that I was able to accomplish all that I needed, but it just would have made my life easier to have know this up front.

