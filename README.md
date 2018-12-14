# pygame zero curriculum

## 01 - helloooWooorld

Use the Pygame Zero documentation to help you complete this assignment:
https://pygame-zero.readthedocs.io/en/stable/

1. Define the draw function. `def draw():` For this project, most of your code will be inside of this function. Draw is a special function that Pygame Zero will automatically call whenever it needs to paint the screen. There is one other function that Pygame Zero will automatically call `def update():` but we will not use it in this project.

2. Fill the screen with a solid color, something other than black or white. https://pygame-zero.readthedocs.io/en/stable/builtins.html#screen

3. Write "Hellooo Wooorld" towards the **center** of the screen. For example, `screen.draw.text("Hellooo Wooorld", topleft=(20, -10))`

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

4. Define a function that will be called when any key is pressed. https://pygame-zero.readthedocs.io/en/stable/hooks.html?highlight=on_key_down#event-handling-hooks In order to run this function when ANY key is pressed, just create the function definition with 0 parameters/arguments. Inside of this function... if the timer has NOT reached the end number, then add a point.

5. Start the clock by calling the clockTick function.

## 03 - arrowControls

1. Set the room to be 800 x 800. https://pygame-zero.readthedocs.io/en/stable/introduction.html

2. Declare a variable called `points` and set it to zero. Declare a variable called `gameOver` and initialize it as `false`

3. Instantiate an Actor named "dude", like this `dude = Actor("alien")` but you may NOT use "alien" or "alien_hurt." Download and add your own transparent PNG sprite. Try to keep the size under 90 x 90. https://codewith.mu/en/howto/pgzero_sounds_images Next, instantiate an Actor that is a coin. Download and add your own transparent PNG coin sprite (size under 90 x 90).

4. Define the draw function and inside this function... Clear the screen. Give it a fill color other than black or white. Draw the points as text on the screen. Draw your Actor dude, like this `dude.draw()` and then draw your coin actor.

5. Define a function called moveCoin. Inside of this function... set coin.x to a random integer between 0 and 800. Do the same thing for coin.y

6. Define a function that will automatically update 60 times a second. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=update#moving-the-alien Inside of this function... If `dude.colliderect(coin)` then add a point and moveCoin. If `keyboard.left` then decrease dude.x by 10, otherwise if `keyboard.right` then increase dude.x by 10. Do the same thing for `keyboard.up` and `keyboard.down`

## 04 - weirdPiano

Map 9 or more keys to various tones, sounds, and music.

1. If `keyboard.a` is pressed https://pygame-zero.readthedocs.io/en/stable/builtins.html#the-keyboard then play a certain tone https://pygame-zero.readthedocs.io/en/stable/builtins.html#tone-generator

2. If `keyboard.s` is pressed, then play a certain sound https://pygame-zero.readthedocs.io/en/stable/builtins.html#sounds You can use `sounds.eep.play()` to test this out. Any sounds that you download or create must be either WAV or OGG.

3. If `keyboard.d` is pressed, then loop a certain piece of music https://pygame-zero.readthedocs.io/en/stable/builtins.html#music MP3s will not work and must be converted to either WAV or OGG. If `keyboard.d` is pressed again, then `music.stop()`

## 05 - sourGrapes

1. An animal and a cluster of grapes (or some other kind of food) appear on the screen.

2. Download a background image that is the size of the game or larger. Use `screen.blit` to display the background image. https://pygame-zero.readthedocs.io/en/stable/builtins.html#images

3. The game ends after 10 or more seconds, the background image changes and the text "Game Over" is displayed. Use a boolean variable called gameOver.

4. Use the arrow keys to move the animal around so they can eat the grapes. The arrow keys work if not gameOver. When the animal touches the grapes, you receive points and the grapes jump to a random, new location.

5. Add sound effects and music. Free CC music at https://freemusicarchive.org/genre/Chiptune/ or https://freemusicarchive.org/search/?quicksearch=8bit

6. Finally, add a predator that slowly chases you. If the `predator.colliderect(animal)` then set gameOver to be true.

## 06 - bouncingOffTheWalls

This project is the Pygame version of the Scratch Bouncing Off The Walls project. Unlike the turtle module, there is no built-in forward(), left(), or right(). We will need to define our own moveForward function.

1. Import random and import math

2. Set the WIDTH to 800 and set the HEIGHT to 800 https://pygame-zero.readthedocs.io/en/stable/introduction.html

3. Instantiate an Actor named "dude", like this `dude = Actor("alien")`

4. Define a function named moveForward with two parameters, someActor and someDistance, like this `def moveForward(someDistance):` and inside this function... convert the actor's angle into radians, like this `radAngle = -math.radians(someActor.angle)` then change the actor's x location by the cosine of that angle, like this `someActor.x += someDistance * math.cos(radAngle)` then change the actor's y location by the sine of that angle, like this `someActor.y += someDistance * math.sin(radAngle)` and finally `return`

5. Define a function named ifOnEdgeBounce with one parameter named someActor, like this `def ifOnEdgeBounce(someActor):` and inside this function... If someActor's x is greater than WIDTH, then moveForward someActor by -10 and set someActor's angle to be 180 - someActor's angle, like this `someActor.angle = 180 - someActor.angle` Do the same thing if someActor's x is less than 0. If someActor's y is greater than HEIGHT, then moveForward someActor by -10 and set someAct's angle to be 360 - someActor's angle. Do the same thing if someActor's y is less than 0.

6. Define the draw function and inside this function... Clear the screen. Fill the screen with a solid color, something other than black or white. Draw your Actor dude, like this `dude.draw()`

7. Define the update function and inside this function... Make dude moveForward by a random amount. Change dude's angle by a random amount. Call the function ifOnEdgeBounce with dude as the argument.

## 07 - obliterationRoom

In this project you will recreate artist Yayoi Kusama's 2002 work "Obliteration Room" in which a white room is slowly transformed by adding brightly colored dot-shaped stickers.
https://www.google.com/search?q=kusama+obliteration+room&tbm=isch

You will create your own class for this project and instantiate objects of this class.

Use the Pygame Zero documentation to help you complete this assignment:
https://pygame-zero.readthedocs.io/en/stable/

1. Set the room to be 400 x 400. https://pygame-zero.readthedocs.io/en/stable/introduction.html

2. Instantiate an Actor named "dude", like this `dude = Actor("alien")` but you may NOT use "alien" or "alien_hurt." Download and add your own transparent PNG sprite. Try to keep the size under 90 x 90. https://codewith.mu/en/howto/pgzero_sounds_images

3. Create two variables called newX and newY and set them both to 300. Create an empty array that will store your dots and name it something like myDots.

4. Implement a Dot class. Each Dot object has 3 unique instance variables (self.x, self.y, and self.color) and 1 method named show(). https://www.w3schools.com/python/python_classes.asp Your class will need a constructor method that will look like this, `def __init__(self, x, y):` and will set the instance variable self.x to x, self.y to y, and self.color to a random color. You class will need a show method that will look like this, `def show(self):` and will draw a filled circle on the screen, like this `screen.draw.filled_circle((self.x,self.y),20,self.color)`

5. Define the draw function and inside this function... Clear the screen. Give it a white fill. Create a for-loop that will loop through your dot array and then draw each dot using i.show(). Draw your Actor dude, like this `dude.draw()`

6. Define a function that will update 60 times a second. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=update#moving-the-alien Inside of this function... if the newX does not equal dude.x, then `dude.x += (newX - dude.x)*.5` and if newY does not equal dude.y, then do the same thing except do it for the y variables. This code will smoothly move your dude so that they always move 50% of the distance between dude's current location and dude's new location.

7. Define a function that will be called when the mouse is clicked. https://pygame-zero.readthedocs.io/en/stable/introduction.html?highlight=on_mouse_down#handling-clicks Inside of this function... Add a new dot to the dot array by appending the current position, like this `myDots.append(Dot(pos[0],pos[1]))`. Also, set newX to be pos[0] and newY to be pos[1]
