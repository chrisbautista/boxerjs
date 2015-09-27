BoxerJS
=======

Yet another jQuery lightbox preview plugin. Why make another one? Making a plugin teaches you Javascript modular pattern and DOM manipulation. Like many  smart programmers would tell you. You learn more with doing than just reading lessons on the matter. If you find my plugin helpful send me a tweet or a like.  Happy coding!



## Problem

> Like many projects you start with the problem. With the problem, you can  set out with a roadmap that will keep you focused on task.

How do I use jQuery to transform my image links into overlay previews?

## Limitations

Let's limit our solution. Limitations produces more creative ideas than freedom. So for these problem I want the solutions to be:

* jQuery
* I have images and thumbnails - each are named as "image.jpg" and "image_thumb.jpg"
* Plugin does not know anything about the images - size or compression.
* Anchors are optional but for semantic purposes and accessibility, thumbnails must be wrapped in anchor tags with a corresponding href reference to the target.
    e.g.
            <a href="my_cool_image.png">
                <img src="my_cool_image_thumb.png" />
            </a>
* Plugin must iterate on a block and not the whole page. 



## Solution

Plugin will iterate on children of blocks converted to boxerJS blocks.  

```html

<div class="boxer">
    <h3>Thumbnails</h3>
    <a href="assets/dog1.jpg" title="Dog 1"><img src="assets/dog1_thumb.jpg" alt="dog 1"></a>
    <a href="assets/dog2.jpg" title="Dog 2"><img src="assets/dog2_thumb.jpg" alt="dog 2" data-pin-nopin="true"></a>
    <a href="assets/dog3.jpg" title="Dog 3"><img src="assets/dog3_thumb.jpg" alt="dog 3" data-pin-nopin="true"></a>
</div>

```


```javascript

    $(".boxer").boxer();

```


TO prevent performance issues, the event listener/callback must be attached to the parent, instead of the child elements. Through event delegation optimize the event loop.

## Installation

1. Download from [https://github.com/chrisbautista/boxerjs](https://github.com/chrisbautista/boxerjs)

```bash

> git clone [https://github.com/chrisbautista/boxerjs](https://github.com/chrisbautista/boxerjs)

or

> wget [https://github.com/chrisbautista/boxerjs/archive/master.zip](https://github.com/chrisbautista/boxerjs/archive/master.zip)

```


## Usage

1. Copy boxer.js, boxer.css, and close.png into your project
2. Include boxer.js and boxer.css
3. Wrap anchors in a container e.g. 

```html

<div class="boxer" > 
   <a href="picture.png" title="this is a picture" > <img src="picture_thumb.jpg" /> </a>
</div >

```

4. Run code 

```javascript

$(".boxer").boxer();

```

