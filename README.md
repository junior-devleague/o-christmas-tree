# o-christmas-tree

O Christmas tree, o Christmas tree
How lovely are thy branches
O Christmas tree, o Christmas tree
How lovely are thy branches!

Let's decorate a cozy place on the web with our very own Christmas tree using HTML's Drag and Drop.

![Final Page Example](https://github.com/junior-devleague/o-christmas-tree/blob/master/assets/example.jpg)

## Objective

Use **HTML Drag and Drop** to allow elements to be dragged into other elements.

## Prerequisites

To complete this project, students should have the following:
* Basic understanding of HTML structures and attributes.
* Basic understanding of Flexbox.
* Basic understanding of JavaScript and DOM

## Instructor Materials

Additional materials needed are as follows:
* Printout of the example layout.

## Your Challenge

### Part 1

To complete Part I, fulfill the following requirements:
1. Set up your project file structure through the command line.
2. Create the following:
* HTML file
* CSS file
* JS file
3. Link all of your files correctly.

### Part II HTML

To complete Part II, fulfill the following requirements:

1. Look at the image above with the example of the final solution. Let's try to recreate the basic structure. But, how do we start?

(Instructor will demo) On your printout of the example layout:
* Circle items on the page that you think can be grouped together. Use the same color when circling to show that those element groupings are siblings to each other. Label the group with how many items are in it, and the type of element.  (e.g. 3 ```divs``` or 9 ```imgs``` ...etc.)
* Show what you think to your instructor. If it is approved, start creating the HTML page in code.

Hint:
Here are the classes and ids that will be used.
* ```id``` of "container"
* ```id``` of "sidebar"
* ```id``` of "sidebar-title"
* ```id``` of "ornament-container"
* ```class``` of "ornament"
* ```id``` of "ornament1", "ornament2", "ornament3"...etc.
* ```id``` of "other-container"
* ```class``` of "other"
* ```id``` of "other1", "other2", "other3"...etc.
* ```id``` of "tree"
* ```class``` of "treepart"
* ```id``` of "treepart1", "treepart2", "treepart3"...etc.

### Part III CSS

To complete Part III, fulfill the following requirements:

1. Target the ```body``` element.
* Set its ```margin``` to 0.
2. Target the ```id``` of "container".
* Set the height to 100vh. vh stands for "view height". 100vh means that the height of the element will fit to the full height of the page.
* Set the width to 100%.
* Activate flex box! *Hint: The property starts with a d...*
3. Target the ```id``` of "sidebar".
* Set the height to 100%.
* Set the width to 450px.
* Activate flexbox!
* Set the direction of items to a column with flex box.
* Center the items horizontally.
* Set a ```box-shadow``` property to ```0 14px 28px rgba(0,0,0,0.25), 0 10px 10px rgba(0,0,0,0.22);```.
4. Target the ```id``` of "sidebar-title".
* Set the width to 100%.
* Set the height to 30px. 
* Activate flex box!
* Center it horizontally and vertically using flex box.
* Give it a background color.
5. Target the ```id``` of "ornament-container".
* Set the width to 70%.
* Set the height to 30%.
* Activate flex box!
* Use flexbox to set the direction of the elements to a column.
* Center the items horizontally and make space around the elements vertically using flexbox.
* Use flexbox to activate wrapping if it occurs.
6. Target the ```class``` of "ornament".  
* Set the height to 30px.
* Set the width to 30px.
* Set the margin to 10px.
* Set the border-radius to 200px.
7. Target the ```id``` of "other-container".
* Set the width to 100%.
* Activate flexbox!
* Set the direction of the elements to a column.
* Horizontally center the items using flexbox.
* Use flexbox to wrap the elements if needed.
8. Target the ```class``` of "other".
* Set the margin to 10px.
9. Target the ```id``` of tree.
* Set the height to 100%.
* Set the width to 100%.
* Activate flexbox!
* Set the direction of the elements to a column.
* Center the items horizontally and vertically.
10. Target the ```class``` of "treepart".
* Set the height to 50px.
* Set the background color to rgb(240, 240, 240) for a light grey color. You can use your own if you prefer.
* Set the top margin to 20px.
* Activate flexbox!
* Use flexbox to make horizontal space around the elements within it.
* Center the items vertically with flexbox.
* Set the box-shadow property to ```inset 0 0 10px #000000;```. This creates an inner black shadow that helps users see that something needs to be dropped in here.
11. Target the ```id``` of treepart1.
* Set the height to 100px.
* Set the width to 100px.
12. Target the ```id``` of treepart2.
* Set the width to 50px.
13. Target the ```id``` of treepart3.
* Set the width to 100px.
14. Target the ```id``` of treepart4.
* Set the width to 150px.
15. Target the ```id``` of treepart5.
* Set the width to 200px.
16. Target the ```id``` of treepart6.
* Set the height to 150px.
* Set the width to 500px.

### Part IV Drag and Drop

To complete Part IV, fulfill the following requirements:

Any element can be dragged in HTML5. These are the general steps to dragging and dropping an element1 into an element2.

1. Make the element draggable.
2. Tell the computer what we want to do when we drag.
3. Make the other element droppable.
4. Tell the computer what we want to do when we drop an element in it.

In your HTML:
1. Make the element draggable: **Create an attribute called ```draggable``` on all of your ornamental elements and set that equal to "true".**
2. Tell the computer what we want to do when we drag: **Create an attribute called ```ondragstart``` on all of your ornamental elements  and set that equal to a function "drag(event)".** Our function's name will be drag, and it will take in the drag event.
3. Make the other element droppable.**On all the elements with the class of ```treepart```, create an attribute ```ondragover``` and set that equal to a function "allowDrop(event)".** This makes the element "droppable".
4. Tell the computer what we want to do when we drop an element in it.**On all the elements with the class of ```treepart```, create an attribute ```ondrop``` and set that equal to a function "drop(event)".**  

Now that we've set that up, let's work in our JS file to create the 3 functions we need: drag(event), allowDrop(event), and drop(event).

In your JS:
1. Create a function called drag that will take in a parameter. This parameter will be the drag event so we can abbreviate it with e or ev as follows:
``` JavaScript
function drag(ev) {
  //more code goes in here!
}
```
This function will get information about the element we are holding and retrieve its ```id```.

``` JavaScript
function drag(ev) {
  ev.dataTransfer.setData('text', ev.target.id);
}
```

Since ```ev``` is a placeholder for our drag event, we will get information about the element being dragged when a drag is triggered. How do we know which element that is? Well, we will grab the ```id``` of our ev.target (the element that fires off the drag event) and set that to a text data type so we can retrieve it later.

2. Create a function called allowDrop that will take in an event as a parameter. By default, we cannot drag elements into other elements (try it!). So, we need to prevent the default functions from running. Fortunately, the event object already has a method called ```preventDefault()``` to help us with that. Call the preventDefault method from the event parameter. *Hint: How do we usually call methods from objects?*

3. Create a function called drop that takes in an event as a parameter. When we drop the element, we want to append the element we are dragging onto the drop space.
* Create a variable ```data``` that will store the element we are holding. We can do that by using ```ev.dataTransfer.getData('text')```. Remember how we stored our element's id into that?
* Now, that we have the id, use the ```appendChild``` method to append our draggable element onto the element we want it to be dropped in. *Hint: Use ```ev.target```, ```appendChild``` and ```document.getElementById()```!*

Resource: https://www.w3schools.com/html/html5_draganddrop.asp

### Part V JS

To complete Part V, fulfill the following requirements:

1. Create an Event Listener on your three gifts that will listen for a click. If you click on it, change the source of the image to an image of something you want for Christmas!

### Stretch Goals
1. Create a button in your sidebar that will generate new ornaments to be added to our tree on click! These ornaments can be in the form of small, circular divs. *Hint: Use ```Event Listeners```, ```createElement```, and ```appendChild```.
