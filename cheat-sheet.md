Coding Club Cheat Sheet

What every HTML Document must have: 
`<!DOCTYPE html>
<html>
    <head>
    </head>

    <body>
    </body>
</html>`

Some elements:

`<div>A div is a place you can put stuff</div>`

If we want to change how things look we can move style in between the <head></head> tags:

`<head>
    <style>
    </style>
</head>`

For instance, we could change the background color of all divs like this:

`<style>
    div {
        background-color: blue;
    }
</style>`

We could also change the size and color of all divs:

`<style>
    div {
        background-color: blue;
        height: 50px;
        width: 50px;
    }
</style>`
 

To give a div a special name:
`<div id=“special-name”></div>` 
Some JavaScript:

We can store things in variables for later:
`var a = “hello world”;`

To make a variable that helps us find a div with a special name:

var specialDiv = document.getElementById(“special-name”);

To change the style of our specialDiv:

`specialDiv.style.backgroundColor = “yellow";

specialDiv.style.width = “100px”;`

When users do things like click and press keys, that is called an event. If we want the computer to do things when there are clicks and button presses we can use events.

To listen for clicks:

`specialDiv.addEventListener(“click”, function(event) {
    console.log(event);
});`
