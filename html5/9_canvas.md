# Canvas

One of the most exciting additions to web pages to be standardized by HTML5 is the canvas element.

    <canvas id="mycanvas"></canvas>

This simple element allows users to draw graphics such as lines, circles, and fills directly into a rectangle-shaped block element that appears on the web page.

## Drawing on a canvas

    <canvas id="mycanvas"></canvas>

The canvas element can have “fallback” content inside the tag, which the browser will render only if canvas itself is not supported.

Alternatively, you can create a canvas element dynamically, append it to the page, and then use CSS to position it where you need it.

    var mycanvas = document.createElement("canvas");
    mycanvas.id = "mycanvas";
    document.body.appendChild(mycanvas);

To draw into the canvas element, first get a reference to the canvas element’s context and then issue drawing commands against that reference.

    var mycanvas = document.getElementById("mycanvas");
    var mycontext = mycanvas.getContext("2d");
    mycontext.beginPath();
    mycontext.moveTo(10, 10);
    mycontext.lineTo(35, 35); // draw a line path from (10,10) to (35,35)
    mycontext.strokeStyle = "#000";
    mycontext.stroke(); // draw the line

In canvas, the order of how you draw things is important, as the last drawing operation for any pixel is the one that is visible.

## The canvas API

Here are some commonly used drawing commands in the canvas API:

### beginPath()

Start a path segment definition, to be used by a rendering operation like stroke() or fill().

### closePath()

Close the path by adding a line segment from the end of the path back to the beginning of the path.

### moveTo(x, y)

Move the registration point for the next relative drawing operation.

### lineTo(x, y)

Create a line path from the current registration point to (x,y).

### rect(x, y, width, height)

Create a rectangle path where (x,y) is one corner, and the diagonally opposite corner is (x+width,y+height).

### arc(x, y, radius, startAngleRadians, endAngleRadians, antiClockwiseDirection)

Create a circular arc path (up to a full circle), where (x,y) is the center of the arc and the arc starts and ends at the given angles (in radians) and moves in either a clockwise or counter-clockwise direction.

### fill()

Fill in the most recently defined path segment.

### stroke()

Stroke (i.e., render, make visible) the most recent path segment.

### drawImage(image, ...)

Draw an image into the canvas area.

### strokeText(text,...) & fillText(text,...)

Add text to the canvas .

### clearRect(x, y, width, height)

Clear a rectangular portion of the canvas from (x,y) to (x+width,y+height).

### strokeStyle=[string|object] & fillStyle=[string|object]

Set the color/style attributes for strokes or fills, respectively.

## Setting canvas Dimensions

Add the width and height attributes, and their corresponding values, to your canvas element.

    <canvas id="mycanvas" width="200" height="200"></canvas>

## Geometric Transformations

The canvas API provides several commands for transforming your canvas drawing actions.

translate(x, y)

- Move/skew the location of the origin point for the coordinate system from (0,0) to (x,y).

scale(x, y)

- Scale the units of the coordinate system in the x and y directions, independently.

rotate(angle)

- Rotate the coordinate system about the origin point, (0,0), by the angle (moving in a clockwise direction) specified in radians.
