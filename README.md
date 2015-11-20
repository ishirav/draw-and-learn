# Draw and Learn

This project provides a fun way to teach kids Python. Instead of doing boring textual programs, they can create fun programs that draw things.

To install the package run:
```
pip install draw-and-learn
```

Here's a minimal program that opens a window and draws a rectangle inside it:
```python
from draw import Window
w = Window()
w.rect(150, 150, 300, 250, color='orange', thickness=5)
w.wait()
```

There are 4 lines in this short program:

1. importing draw-and-learn's Window class
2. creating a window
3. drawing a rectangle inside the window
4. waiting for the user to close the window

## The Window class

A Window provides a "canvas" for drawing. All drawing must be performed inside a Window. 
This class provides the following methods and properties:

### Constructor

When creating a window you can specify the following parameters:

* `width` - The window's width in pixels (optional, defaults to 800).
* `height` - The window's height in pixels (optional, defaults to 600).
* `title` - the window's title (optional, defaults to "Draw and Learn").

For example:
```python
w = Window(width=500, height=500, title='My masterpiece')
```
### width

This property returns the window's width.

### height

This property returns the window's height.

### wait()

This method must be called after drawing inside the window. This prevents the window from closing immediately, 
and waits for the user to close it.

### line(x0, y0, x1, y1, color='black', thickness=1)

Draws a line inside the window, from the point `(x0, y0)` to the point `(x1, y1)`.

Optional parameters:

* `color` - specified the line color using any of the color names here: http://www.tcl.tk/man/tcl8.5/TkCmd/colors.htm (defaults to black).
* `thickness` - the line thickness in pixels (defaults to 1).

For example:
```python
w = Window()
# Draw a 1-pixel-thick black line 
w.line(20, 20, 700, 20)
# Draw a 5-pixel-thick red line
w.line(20, 50, 700, 50, color='red', thickness=5)
```

### rect(x0, y0, x1, y1, color='black', thickness=1, fill='')

Draws a rectangle inside the window, with one corner at `(x0, y0)` and the other at `(x1, y1)`.

Optional parameters:

* `color` - specified the rectangle's outline using any of the color names here: http://www.tcl.tk/man/tcl8.5/TkCmd/colors.htm (defaults to black).
* `thickness` - the rectangle's outline thickness in pixels (defaults to 1).
* `fill` - the color to fill the rectangle with (defaults to outline only, with no fill).

For example:
```python
w = Window()
w.rect(100, 100, 200, 300, color='black', thickness=10, fill='grey')
```

### circle(x, y, radius, color='black', thickness=1, fill='')

Draws a circle of the give radius, centered at `(x, y)`.

Optional parameters:

* `color` - specified the circle's outline using any of the color names here: http://www.tcl.tk/man/tcl8.5/TkCmd/colors.htm (defaults to black).
* `thickness` - the circle's outline thickness in pixels (defaults to 1).
* `fill` - the color to fill the circle with (defaults to outline only, with no fill).

For example, to draw a blue circle with a radius of 50 pixels at the center of the window:
```python
w = Window()
w.circle(w.width / 2, w.height / 2, 50, color='blue')
```

### clear()

Erases everything that was drawn in the window.


## Helper Methods

### rgb(red, green, blue)

Creates a color string from its red, green and blue parts (each is expected to be a number from 0 to 255).
