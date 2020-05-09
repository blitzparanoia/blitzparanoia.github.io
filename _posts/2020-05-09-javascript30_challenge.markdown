---
layout: post
title:      "JavaScript30 Challenge"
date:       2020-05-09 14:40:20 -0400
permalink:  javascript30_challenge
---

## Day 1- JavaScript Drum Kit

The goal was to create a drum kit app that responded to the user pressing a corresponding key on their keyboard and playing the sound associated to that key.

**Demo the app at this link**: [JS Drum Kit](https://jsdrumkitapp.herokuapp.com/index.html)

**Git Hub Repo**: [GitHub Files](https://github.com/blitzparanoia/my-javascript30)

## Highlights

**Use of the HTML data-* attribute**

HTML 5 feature gives coders the ability to create their own attribute. If you want to create a specific attribute to hold data. The values of data can be read using JavaScript. The data attributes can also be accessed using CSS to change styles. This is because they are treated like plain HTML attributes.

**Use of `<kbd>` element**

A HTML Keyboard Input element that represents user input from a keyboard, it is displayed in a default monospace font and can be styled in CSS.

**JS Event Listeners**

Event listeners were used on the window to listen for the keydown input. The triggering of an event listener calls the playSound function.

**JS document.querySelector**

Document.querySelector was used to connect the audio attribute to the corresponding keyCode. Each key has a unique identifying key code via ASCI-II number. The audio has check logic `if  (!audio) return;` to ensure events only get fired when a matching key listed is pressed.

**classList**

The keys were assigned to a variable in the playSound() in order to add the animation when playing. When a key is pressed a yellow border quickly flashes and the scale changes. In vanilla JS this is accomplished by `key.classList.add(‘playing’)` which added the change to the element. However, when changes are added they have to be removed to return to the previous state. This was achieved by identifying all the keys on the document via `document.querySelectorAll`. Since the keys are all part of a node list of elements it is possible to use the `.forEach` ES6 feature to iterate over the keys and add the transition end event listener to remove the transition. The removeTransition() identified if there was a change to the transform property and then to remove the change with `this.classList.remove(‘playing’)`

**CSS rem Unit**

In the style.css doc note the use of the rem unit for font sizing. It means that the font sizes are referenced from the root element font size. `rem` stands for root em. The docs provide a nifty example to modify the code and explore rem vs. em units.
Docs: https://developer.mozilla.org/en-US/docs/Learn/CSS/Building_blocks/Values_and_units

**🥳Take Away**

The drum kit was really fun to make. I learned how to use HTML data-, practiced with CSS styling, using `classList` from vanilla JS and worked with incorporating audio/sound files. I am looking forward to continuing sharpening my JavaScript knowledge without the use of libraries. 

