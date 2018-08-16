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

1. Declare a points variable and set it to 0. Declare a timer variable and set it to something like 5.

2. Define a function called clockTick. Inside this function... Change the timer by 1. Print the timer to the console. If the timer has NOT reached the end number, then schedule a clockTick to occur in 1 second. https://pygame-zero.readthedocs.io/en/stable/builtins.html?highlight=clock#clock

3. Define the draw function and inside this function... Clear the screen. Draw the timer as text on the screen and then draw the points as text on the screen. If the time HAS reached the end number then change the fill color for the screen. https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen

4. Define a function that will be called when the mouse is clicked. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=on_mouse_down#handling-clicks Inside of this function... if the timer has NOT reached the end number, then add a point.

5. Start the clock by calling the clockTick function.

## 03 - arrowControls

1. Set the room to be 800 x 800. https://pygame-zero.readthedocs.io/en/stable/introduction.html

2. Declare a variable called `points` and set it to zero. Declare a variable called `gameOver` and initialize it as `false`

3. Instantiate an Actor named "dude", like this `dude = Actor("alien")` but you may NOT use "alien" or "alien_hurt." Download and add your own transparent PNG sprite. Try to keep the size under 90 x 90. https://codewith.mu/en/howto/pgzero_sounds_images Next, instantiate an Actor that is a coin. Download and add your own transparent PNG coin sprite (size under 90 x 90).

4. Define the draw function and inside this function... Clear the screen. Give it a fill color other than black or white. Draw the points as text on the screen. Draw your Actor dude, like this `dude.draw()` and then draw your coin actor.

5. Define a function called moveCoin. Inside of this function... set coin.x to a random integer between 0 and 800. Do the same thing for coin.y

6. Define a function that will update 60 times a second. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=update#moving-the-alien Inside of this function... If `dude.colliderect(coin)` then add a point and moveCoin. If `keyboard.left` then decrease dude.x by 10, otherwise if `keyboard.right` then increase dude.x by 10. Do the same thing for `keyboard.up` and `keyboard.down`

## 04 - obliterationRoom

In this project you will recreate artist Yayoi Kusama's 2002 work "Obliteration Room" in which a white room is slowly transformed by adding brightly colored dot-shaped stickers.
https://www.google.com/search?q=kusama+obliteration+room&tbm=isch

Use the Pygame Zero documentation to help you complete this assignment:
https://pygame-zero.readthedocs.io/en/stable/

1. Set the room to be 400 x 400. https://pygame-zero.readthedocs.io/en/stable/introduction.html

2. Instantiate an Actor named "dude", like this `dude = Actor("alien")` but you may NOT use "alien" or "alien_hurt." Download and add your own transparent PNG sprite. Try to keep the size under 90 x 90. https://codewith.mu/en/howto/pgzero_sounds_images

3. Create two variables called newX and newY and set them both to 300. Create an empty array that will store your dots.

4. Define the draw function and inside this function... Clear the screen. Give it a white fill. Create a for-loop that will loop through your dot array and then draw each dot as a filled circle. Draw your Actor dude, like this `dude.draw()`

5. Define a function that will update 60 times a second. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=update#moving-the-alien Inside of this function... if the newX does not equal dude.x, then `dude.x += (newX - dude.x)*.5` and if newY does not equal dude.y, then do the same thing except do it for the y variables. This code will smoothly move your dude so that they always move 50% of the distance between dude's current location and dude's new location.

6. Define a function that will be called when the mouse is clicked. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=on_mouse_down#handling-clicks Inside of this function... Add a new dot to the dot array by appending the current position. Also, set newX to be pos[0] and newY to be pos[1]

Implement a Dot class. Each Dot object has 3 unique instance variables (x, y, and color) and 1 method ( drawDot() ).

## 05 - sourGrapes

An animal and a cluster of grapes (or some other kind of food) appear on the screen. Download a background image that is the size of the game or larger. Use `screen.blit` to display the background image. https://pygame-zero.readthedocs.io/en/stable/builtins.html#images Use the arrow keys to move the animal to eat the grapes. When the animal touches the grapes, you receive points and the grapes jump to a random, new location. The game ends after several seconds, the background color changes and the text "Game Over" is displayed. Use a boolean variable called gameOver. If not gameOver then the arrow keys work. Finally, add a slow predator that chases you. If the `predator.colliderect(animal)` then set gameOver to be true.
