LennyGUI
========

API to make pretty GUIs in Computercraft for Minecraft

###Features:

1. Full error handling, clearly tells you what you did wrong
2. Buttons
3. Shapes (rectangles & lines)
4. Ablilty to create clickable reagons of the screen that aren't drawn as buttons and similarly to create boxes with text that look like buttons, but don't trigger anything
5. Customizable text color & background color

###Functions:

1. ```gui.button.add(text, function, x, y, spacing, height, textcolor, backgroundcolor)``` - Draws a button on the screen, returns ID which can be used for certain operations
2. ```gui.button.draw(text, x, y, spacing, height, textcolor, backgroundcolor)``` - One of the two functions that gui.button.add uses, draws what appears to be a button, but dosen't do or return anything
3. ```gui.button.index(function, x1, y1, x2, y2, isdrawn [,tcolor, bcolor, text])``` - Creates a clickable region which acts like a button, is the second function used by gui.button.add. If you're creating just a clickable region then the 'isdrawn' argument should be false and the last 3 should be excluded
4. ```gui.button.gray(ID)``` - Either grays out or ungrays a button rendering it unclickable, if you are just disabling a clickable region, gui.button.gray will not attempt to draw a gray button, but instead just disable it.
5. ```gui.shape.rect(x, y, width, height, color)``` - Draws a rectangle, but relies on gui.shape.altrect.
6. ```gui.shape.altrect(x1, y1, x2, y2, color)``` - Also draws a rectangle, but using coord1 and coord2 rather than coord and width.
7. ```gui.shape.line(x1,y1,x2,y2,color)``` - Basic line algoritm
8. ```gui.fill(x, y, color [, char])``` - Fills a single pixel with the specified color or charecter using the preset textcolor.
9. ```gui.progbar.add(x, y, width, percent, forecolor, backcolor)``` - Craetes a progress bar already at the specified percent (or 0), returns ID  for use with next 2 functions
10. ```gui.progbar.increment(ID, percent)``` - Increments the percent of the progress bar with ID given by percent, returns total percent.
11. ```gui.progbar.set(ID, percent)``` - Sets percent of progress bar with ID given to percent.

####Control Methods

1. ```start()``` - Simple enough, engages in an infinite loop which checks if a button is clicked and runs the apropriate user-defined function
2. ```stop()``` - Stops the click checking method *Hint: because ```start()``` is an infinite loop, to use ```stop()```, the routine that does it must be run using the parallel API*

	More to come...