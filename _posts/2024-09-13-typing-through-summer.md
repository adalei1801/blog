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

<img src="/blogs/images/fonts.jpeg" alt="Photo of font options">
<p style="font-size: 12px;">Fonts choices</p>

I picked fonts that I thought were fun looking but still legible (Playwrite and Bebas Neue), some fonts I picked because they were recognizable (Times New Roman and Roboto), and others were favorites of mine (Courier New). The process of picking fonts was fun as I got to see the cool fonts that were out there and create a framework for future additions to the playground.

Working to put these fonts in the playground came with an odd set of challenges. One of which was actually getting them in the code. Originally, I used the @import option the Google Fonts had in order to add their fonts to code but it did not work as uniformly as I wanted it to so I had to pivot. The second (and operational) idea I had was to use the link tag option to add the fonts which worked. 

```html 
<link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Playwrite+US+Trad:wght@100..400&family=Sofia&display=swap" rel="stylesheet">

    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Roboto:ital,wght@0,100;0,300;0,400;0,500;0,700;0,900;1,100;1,300;1,400;1,500;1,700;1,900&display=swap" rel="stylesheet">
```
<p style="font-size: 12px;">Code snippet for the first two fonts (Playwrite USA Traditional & Roboto). Second idea of using the link tag to make the fonts work.</p>

Now that the fonts were in, I could make the menu and buttons for them. This was not difficult as everything just went into a hover over menu but changing the fonts on the button options was difficult as Playwrite option was in Times New Roman instead of its own font. The issue stemmed from a syntax error in the CSS where the font family I used for Playwrite was cursive, but since CSS does not support a formal cursive font family, I used sans-serif instead.

```css
#playwriteBtn {
    font-family: "Playwrite US Trad", sans-serif;
}
```
<p style="font-size: 12px;">CSS for Playwrite button. The use of sans-serif allowed the button to be in its correct font</p>

Similar to the color buttons changing the button colors as well, I decided to do the same for the fonts. This was not as difficult as I had to do so for colors.

## Change Text

The last large addition to the playground was the ability to add text. The coding was simple as I made a hover menu like I did for the other options and used the text area tag to get the user’s text and the .innerHTML JavaScript property to change the text according to user input. 

```html
<textarea name="text" row="5" cols="30" id="textInput"></textarea>
```
<p style="font-size: 12px;">The text area used to collect user input.</p>

```javascript
function changeText () {
    text.innerHTML = textEdit.value
}
```
<p style="font-size: 12px;">The JavaScript function used to change the text</p>

Problems arose when typing caused the screen to close. To fix this problem I had to make a menu that would stay open. The first idea I researched was complicated for my current skill so I decided to use CSS to keep the window open by using the display property. When the “Change Text” button was clicked it would change the menu’s display from “none” to “block.” Making the “Change Text” button also the close button was also difficult, so I added a close button to the menu that would change the display from “block” to “none.”

```javascript
function showContent () {
    textContent.style.display = 'block'
}

function hideBox () {
    textContent.style.display = 'none'
}
```
<p style="font-size: 12px">Functions to show the menu using the Change Text button and hide it with the close button</p>

## Future Changes & Conclusions

I plan to make other changes in the future like fixing the style buttons and possibly adding the ability to change font size.

I found this experience fun and challenging. I am proud of the work I did and I hope I can find new ways to add to it.

Here’s the link if you want try it: https://adalei1801.github.io/AltText/ 
