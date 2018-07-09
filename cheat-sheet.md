Coding Club Cheat Sheet

What every HTML Document must have: 

`<html>
    <head>
    </head>
    <body>
    </body>
</html>`

A DOCTYPE lets our browser know what html rules it should expect
html is the container of the everything
head is the container for invisible important things such as: metadata (like the title of your web page), external files and special rules
body represents what we shall actually see displayed on our website.
Any element that you want to add to a web page must be enclosed within the tag

This is how you specify comments in html code. Comments can be anything - additional information to explain what your code does, what a particular element is going to be used for etc.

`<!-- Here is a comment that will be ignored -->`

Some elements:

A paragraph tag will keep a series of sentences together.
`<p>This is a paragraph</p>`
<p>Multiple paragraphs will have space between them.<p>`

Sometimes you may want to stress the importance of certain words for which you can use the strong tag
`<p><strong>Caution:</strong> Before proceeding, make sure you have your coding helmet on</p>`

Sometimes you may want to place emphasis on specific words, for which you can use the em tag
`<p>I <em>love</em> coding!</p>`

You can group sections of your html page in a div container which you can then apply styling to.
This container can hold any kind of content such a p
`<div>A div is a container where you can put other stuff. This creates a new block</div>`

The span is an inline generic container usually used to group elements together for styling purposes
`<p>This is a paragraph with <span>a span which is like a div, but is inline</span> which means it doesn't make a new block.</p>`

The img tag can be used to insert images into your web page
`<img src="http://placekitten.com/200/300"/></img>`

The a element allows you to add links to other web pages:
`<a href="http://www.google.com/">A link will take us somewhere else.</a>`

If we want to change how things look we can move style in between the head tags:

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

And we could change the color of the text of the paragraph like this:

`<style>
    p {
        color: red;
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

where px stands for pixels

To give a div a special name:
`<div id=“special-name”></div>` 

You can have multiple div elements in your page, which have different content. These div blocks can be styled independently.

`<body>
    <div id="Div1">
        <p> This paragraph is in Div1 </p>
    </div>
    <div id="Div2">
        <p> This paragraph is in Div2 </p>
    </div>
</body>`

We can style the above to <div> blocks to be of different colors using the <style> tag:

`<head>
    <style>
        #Div1 {
            background-color: lime;
        }

        #Div2 {
            background-color: coral;
        }
    </style>
</head>`

If you provide a generic styling for div blocks, that will be the default for all div blocks unless there is a more specific assignment using the block's special name. Taking the above example of two div blocks called Div1 and Div2:

`<head>
    <style>
        div {
            background-color: blue;
        }
        #Div1 {
            background-color: lime;
        }
    </style>
</head>`

In the above case, Div1 will be colored "lime", and Div2 will take the color specified for all <div> blocks which is blue. If there is no styling specified for a generic <div> block, then no color will be applied to Div2.

The above styling rules apply to all elements in the html page.

Some other styling parameters to play around with:

**Border**

`<html>
    <head>
        <style>
            div {
                /* border: style */
                border: solid
                /* border: width | style */
                /* border: 2px dotted */
                /* border: width | style | color */
                /* border: medium dashed green */ 
            }
        </style>
    </head>
    <body>
        <div>
            <p>This is my first paragraph.</p>
            <p>And this is my second paragraph, both of which are enclosed in a border</p>
        </div>
    </body>
</html>`

**Margin**

`<head>
    <style>
        div {
            border: solid;
            /* To add space around the outside of an element, in this case the div element */
            margin-top: 10px;
            margin-bottom: 10px;
            margin-right: 20px;
            margin-left: 20px;
              
            /* Another way to write this: */  
            /* margin: 10px 20px;*/
            /* first value applies to top & bottom, second value applies to right & left */
        }
    </style>
</head>`

**Padding**
`<head>
    <style>
        div {
            /* Use padding to add spacing around the content */
            padding:10px 20px 20px 20px;
            /* top | right | bottom | left */
        }
    </style>
</head>`

**Font-family**

`<html>
    <head>
        <style>
            div.monospace {
                font-family: monospace;
            }
            div.cursive {
                font-family: cursive;
            }
            div.georgia {
                font-family: georgia;
            }
        </style>
    </head>
    <body>
        <div class="monospace">
            This text is in Monospace font.
        </div>

        <div class="cursive">
            This text is in Cursive font.
        </div>

        <div class="georgia">
            This text is in Georgia font.
        </div>
    </body>
</html>`

Some JavaScript:

We can store things in variables for later:
`var a = “hello world”;`

To make a variable that helps us find a div with a special name:

`var specialDiv = document.getElementById(“special-name”);`

To change the style of our specialDiv:

`specialDiv.style.backgroundColor = “yellow";

specialDiv.style.width = “100px”;`

When users do things like click and press keys, that is called an event. If we want the computer to do things when there are clicks and button presses we can use events.

To listen for clicks:

`specialDiv.addEventListener(“click”, function(event) {
    console.log(event);
});`

addEventListener: This tells the web page to add a listener for an event on the <div> element, and to take some action when the event occurs

There are two parameters that are passed to the addEventListener function:

Parameter 1: "click", this instructs the page to listen for the click event
Parameter 2:
`function(event){
    console.log(event);
}`
This is a lambda function. This contents of this function determines what is executed when the click event occurs. In this case, the details of the event are logged to the console. (On Chrome, if you open the Web Developer Tools, open the console tab, you will see this eventl logged whenever a click on the <div> occurs).

You can add a listener to take action whenever the user presses a key:

`specialDiv.addEventListener(“keypress”, function(event) {
    console.log(event);
});`

