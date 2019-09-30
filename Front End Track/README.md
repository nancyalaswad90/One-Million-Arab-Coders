# Front-End-Development

![image](https://user-images.githubusercontent.com/36210723/65848119-40c2b580-e34d-11e9-8e71-2e1c0133fddb.png)


## Lab ( 1 ) 

# Animal Trading Card Instructions

The Lab starts with the following files:

* `card.html`
* `clownfish.jpg`
* `design-prototype.jpg`
* `styles.css`

Your job is to try and recreate what you see in the `design-prototype.jpg`. You’ll need to modify `card.html` to include `attributes` and use CSS `selectors` to style specific elements.

## ⚠️ Important ⚠️

**Please do not remove or alter any existing `id` attributes in `card.html`!**

The `card.html` file comes with some initial HTML. A few HTML elements already have `id` attributes. The validation code _requires_ these exact `id`s on these exact elements, so do not remove them or the validation will fail.

## 🛠 Required Changes ⚙️

Make the following changes to `card.html`

1. Change the heading to the name of your favorite animal
2. Replace the placeholder image with your favorite animal's image.

    Also, change the image's `alt` attribute to the name of your animal.
    So, `alt="name-of-your-animal"` should be replaced with the actual name of your animal.

    Note: You will want to use an image with a `width` of 300 pixels. If your image is larger, you can set the image's width to 300 pixels in your CSS, but be aware that your image might end up squished or distorted. Later, we’ll talk about how you can fix this problem using responsive images.

3. Edit the interesting fact paragraph
4. Edit the key characteristics
5. Edit the informational paragraph

## 💃 Style the Page 🕺

The CSS must apply these styles to match the design prototype:

  1. link your stylesheet `styles.css` to the HTML or else your CSS will not be applied.
  2. give the interesting facts `<div>` a CSS class of `animal-info`
  3. italicize the text for the animal's interesting fact
  4. bold the labels for the animal's list items (e.g. 'Habitat')
  5. remove dots from the animal's list items
  6. add a border around the animal's name, image, and information
  7. add a border around the animal's information
  8. add spacing between the animal's name, image, and information (you will need to use the property [padding](https://developer.mozilla.org/en-US/docs/Web/CSS/padding))

## ✅ Test Your Code ❌

To pass the Lab, follow the instructions above to get `card.html` to render similarly to what's seen in `design-prototype.jpg`.

To test how close you are, click the "RUN CODE" button located in the bottom right of the Workspace. This will run the validator against your code. A popup window will appear and run through all of the tests. If something still needs to be done, it will appear in this popup window in red. Also, there's no limit on the number of times you can use the "RUN CODE" feature, so keep checking it until you pass!

Good luck!










## Lab ( 2 )

## Instructions

### Get the Starter Code

If you'd like to start from scratch without any files, feel free to do so! You learn the most by developing on your own! But, it can be a bit challenging having to start from scratch, so we do provide some starter code to use.

The starter code includes all required HTML input fields, as well as some basic styling. A skeleton of the makeGrid() function is provided as well.

### Development Strategy

Before writing any code, try loading up index.html from the starter project to see how things look! Notice that the design.js file is implemented in the <body> tag in the index.html file. Your goal is to build out the design.js file to achieve all the interactive elements on the page!

Now, open up design.js. As you start writing your code, keep these three tasks in mind:

Define your variables by selecting the DOM elements that the user will interact with. This is where your DOM skills can come into play! For instance, the submit button, the table, and the color picker need to be accessed. The value of the color selected needs to be stored as well, since the clicked cell in the table needs to be set to the selected color.
Add event listeners to the relevant DOM elements, so that user input can be color values and table sizes can be dynamically set by the user.

Set the size of the cross stitch canvas as an _N_ by _M_ grid with the makeGrid() function. Use your knowledge of JavaScript loops to dynamically clear and create the table based on user input. Each cell should have an event listener that sets the background color of the cell to the selected color.
Now test it! When you're done, you should be able to create a canvas of any size, choose a color using the color picker, and click on the canvas's table cells to set their color.

### Note: To complete Pixel Art Maker, you must be using the current version of Edge, Firefox, or Chrome. Due to implementation differences, this exercise does not work effectively in Safari or Opera.

Udacity Style Guides

The starter contains basic styling, but feel free to style the app as you please! You should write your code and markup to meet the specifications provided in these style guides:

CSS Style Guide

HTML Style Guide

JavaScript Style Guide

Git Style Guide

https://codepen.io/nancyalaswad90/pen/GVJELB
