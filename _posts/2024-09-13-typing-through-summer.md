# Typing Through Summer: The Making of Alt Text

## Introduction

Over this summer, I fell into making a playground. 

At the beginning of my summer break I found myself fiddling with the W3Schools editor. I was testing code for a separate project and eventually started experimenting with the buttons. I had fun changing the text colors with them and copied the code to see if I could do something with it later. 

When later rolled around (a couple of weeks), I decided to see if I could make other changes to the text. I started out with fonts, then moved on to styles, and then experimented with changing the text itself.

## Colors

Changing the text color was the beginning and the easiest part of this process (but it did have its challenges). I used the colors of the rainbow for the first set of colors and later added pink, black, white, and gray. I also had the idea to make the button text color match the color it changed the text to which was not extremely difficult. 

The first minor issue of the project then cropped up as not all of the colors (yellow, white, and pink) were visible on the white background so I had to make the background of the words black for those colors (I decided later on that pink was visible enough on white). The background was also black on the buttons in their default position. 

The second issue that came up was the black background being on colors that did not need it, so I gave the text an id in JavaScript and used it to change the background color depending on the font color. 

``` javascript
let whiteSet = document.getElementById('text')
```
<p style="font-size: 12px;">Assigning text a JavaScript id to change the background color</p>

I decided to change the buttons and the divider lines to match the font color. This choice came with some minor issues as adding new buttons meant I had to go back and add them to all of the functions. 

Eventually, I came up with a template that the color buttons followed in order to change what needed to be changed (with small variations between the options).

```javascript
function colorRed () {
document.body.style.color = 'red'
whiteSet.style.backgroundColor = 'transparent'
title.style.borderBottomColor = 'red'
title.style.backgroundColor = 'transparent'
line.style.backgroundColor = 'red'
changeColorBtn.style.color = 'white'
changeColorBtn.style.backgroundColor = 'red'
changeFontBtn.style.color = 'white'
changeFontBtn.style.backgroundColor = 'red'
textCover.style.color = 'white'
textCover.style.backgroundColor = 'red'
changeStyleBtn.style.color = 'white'
changeStyleBtn.style.backgroundColor = 'red'
}
```
<p style="font-size: 12px">Function for the color red button. This setup is used for the other colors with variations in background values.</p>

## Fonts
I used Google Fonts to find some that I liked and I choose: 

<ul>
<li>Times New Roman</li>
<li>Courier New</li>