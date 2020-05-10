---
layout: post
title:      "Day 2- CSS + JS Clock"
date:       2020-05-10 14:11:20 -0400
permalink:  javascript30_challenge
---

### JavaScript30 Challenge
#### Github Link: [CSS JS Clock]( https://github.com/blitzparanoia/my-javascript30/tree/master/02-css-js-clock)

### Goal
Create a clock that displays the current time with HTML/CSS and pure JS

### Clock Hands
The hands move based on the current hour, minute and seconds that is retrieved from the build in `new Date()` The hands are on top of each other by default. When rotating the hands it is necessary to define the pivot point (by default items rotates at the center) completed by `transform-origin`. The degrees of which the hands need to be moved. This can be tested in the browser inspection tools by modifying the page element with the CSS transition options. Keep in mind that the off setting at 90 degrees needs to be factored in the mathematics, to ensure the hands move to the correct position.

### Moving the Hands
The JS for moving the hands is fairly straight forward. Capture the time in a variable via `new Date()`. Then use the corresponding `.getSeconds()`, `.getMinutes()` and `.getHours()` and save the value to a variable. The style is applied to the respective hand that was “grabbed” via the `document.querySelector()`. When the style is applied to the style transform property we specify the rotation using template literals `${}`.

### 🥳Take Away
Amazed at how quick this project built up. It was very satisfying creating a working clock. I am excited to create other clock versions in the future and customize it further. The math for adding +90 to factor in for the degree offset was tricky and I am glad it was explained. I have to keep in mind that `Console.log();` is my friend when working through code and seeing the data being manipulated. 

