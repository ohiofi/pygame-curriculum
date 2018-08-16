# pygame zero curriculum

## 01 - helloOoWoOorld

Use the Pygame Zero documentation to help you complete this assignment:
https://pygame-zero.readthedocs.io/en/stable/

1. Define the draw function. `def draw():` For this project, most of your code will be inside of this function.

2. Fill the screen with a solid color to something other than black or white. https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen

3. Write "Hello World" towards the **center** of the screen. For example, `screen.draw.text("Hello World", topleft=(20, -10))`

4. Set the text color to something other than black or white. https://pygame-zero.readthedocs.io/en/stable/ptext.html

5. If your text color is light, then give it a dark outline. If your text color is dark, give it a light outline. https://pygame-zero.readthedocs.io/en/stable/ptext.html

6. Use a for-loop to draw a bunch of bubbles `screen.draw.circle` in a straight line. https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen

7. Draw a small square `screen.draw.filled_rect` somewhere at the bottom of the screen. Set it's color to something other than black or white.

8. Use a for-loop and random() to draw a dozen randomly-positioned, random-sized, and randomly-colored polka dots `screen.draw.filled_circle`

## 02 - tickTock

Create a timer that counts down to an end number, then stops
OR
Create a timer that counts up to an end number, then stops

1. Set you timer variable to something like 5

2. Define a function called clockTick. Inside this function... Change the timer by 1. Print the timer to the console.

3. Define the draw function and inside this function... Clear the screen. Draw the timer as text on the screen. If the timer has NOT reached the end number, then schedule a clockTick to occur in 1 second. https://pygame-zero.readthedocs.io/en/stable/builtins.html?highlight=clock#clock If the time HAS reached the end number then change the fill color for the screen. https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen

## 03 - obliterationRoom

In this project you will recreate artist Yayoi Kusama's 2002 work "Obliteration Room" in which a white room is slowly transformed by adding brightly colored dot-shaped stickers.
https://www.google.com/search?q=kusama+obliteration+room&tbm=isch

Use the Pygame Zero documentation to help you complete this assignment:
https://pygame-zero.readthedocs.io/en/stable/

1. Set the room to be 400 x 400. https://pygame-zero.readthedocs.io/en/stable/introduction.html

2. Instantiate an Actor named "dude", like this `dude = Actor("alien")` but you may NOT use "alien" or "alien_hurt." Download and add your own transparent PNG sprite. Try to keep the size under 90 x 90. https://codewith.mu/en/howto/pgzero_sounds_images

3. Create two variables called newX and newY and set them both to 300. Create an empty array that will store your dots.

4. Define the draw function and inside this function... Clear the screen. Give it a white fill. Create a for-loop that will loop through your dot array and then draw each dot as a filled circle. Draw your Actor dude, like this `dude.draw()`

5. Define a function that will update 60 times a second. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=update#moving-the-alien Inside of this function... if the newX does not equal dude.x, then `dude.x += (newX - dude.x)*.5` and if newY does not equal dude.y, then do the same thing except do it for the y variables.

6. Define a function that will be called when the mouse is clicked. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=on_mouse_down#handling-clicks Inside of this function... Add a new dot to the dot array by appending the current position. Also, set newX to be pos[0] and newY to be pos[1]

Implement a Dot class. Each Dot object has 3 unique instance variables (x, y, and color) and 1 method ( drawDot() ).

## 04 - sourGrapes

A fox and a cluster of grapes (a "bunch" of grapes) appear on the screen. Use the arrow keys to move the fox to eat the grapes. When the fox touches the grapes, you receive points and the grapes jump to a random, new location. The game ends after several seconds and your final score is displayed.
