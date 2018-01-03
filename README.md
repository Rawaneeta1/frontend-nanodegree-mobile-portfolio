# Website Performance Optimization portfolio project

This project is a practice on Udacity's course **Website Performance Optimization** which explains how to measure and optimize any website.

## Getting started
* You can check the PageSpeed Insights score for [index.html](https://rawaneeta1.github.io/frontend-nanodegree-mobile-portfolio/index.html) by pasting it's url in [PageSpeed Insights](https://developers.google.com/speed/pagespeed/insights/?url=https%3A%2F%2Frawaneeta1.github.io%2Ffrontend-nanodegree-mobile-portfolio%2Findex.html&tab=desktop)

* You can use the FPS Counter/HUD in Chrome developer tools to find the number of Frames per Second in [pizza.html](https://rawaneeta1.github.io/frontend-nanodegree-mobile-portfolio/views/pizza.html)

## Optimization
### &nbsp;&nbsp;*Index.html*
* Removed render blocking for **Analytic script** that is not critical to initial render by adding `async` attribute.
* Removed render blocking from **css/print.css** CSS styles that are only used under certain conditions by adding `print` media type .
* Minimzed the number of additional HTTP requests blocking initial rendering, by `inlining` critical **style.css** file.
* `Compressed and optimize the used **images.**
* Minified **CSS** and **JavaScript files**.
### &nbsp;&nbsp;*Main.js*
* Replaced all `querySelectorAll` by `getElementsByClassName` to enuser [higher oprations performed per second](https://jsperf.com/getelementsbyclassname-vs-queryselectorall/59) 
* Replaced all `querySelector` by `getElementsById` to enuser [higher oprations performed per second](https://jsperf.com/getelementbyid-vs-queryselector) 
* Reduced the time to resize pizza to less then `5ms` by reducing the cost of accessing the document everytime inside the `changePizzaSizes` loop, and instead access the document one time to find the matching element and store it in a variable.
* Removed calculating the never changing new width of the pizza form inside the `changePizzaSizes` loop.
* Updated `updatePositions` function by removing variables `items` and `scrollTop` from the loop since they're not changin.
* Reduced the number of pizzas from 200 to 48.