# Super Fantastic Drag and Drop Game!
## Drag the piece from the left and complete the puzzle on the right side! 
1. Just complete the puzzle by simply dragging.
2. click the bottom picture to choose the picture you want to play.

## Bug fix
### Bug #1
#### this bug caused because there is no definition for more than one piece in one puzzle zone, the solution is in the folling
1. find the code for manage *drop*, which is start at *js* line 63.
2. Now I need a condition for **e.preventDefault();**，so I use the *if...else statement*, set the condition to **zone.children.length == 0**, which means in each children element inside zone, if there is nothing in it, the picture can be dropped into it. 
3. Then is the **else**, when the *length != 0*, the return is *false*, that means the drop operation is invalid, and the extra piece with return to it original position.
4. All last, I add a console to it, when you try to add more than one piece into one zone, the console while record it.

### Bug #2
#### this bug caused because there is no related command in the function of click the reset button, the solution is below.
1. find the function for reset button, which is start at *js* line 63, I decide run this function after clean up the puzzle pieces, so the related code start at line 88.
2. use **forEach** to select divs inside dropZones, and then use **zone.innerHTML = "";** to clear all the content inside div box. 
