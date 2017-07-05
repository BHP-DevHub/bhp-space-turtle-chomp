## Part 4 – Create an objective (chomping space cabbage) and collision checking {#part-4-create-an-objective-chomping-space-cabbage-and-collision-checking}

OK so now you have your turtle that we can move around the screen and if we bump into any of the boarders your turtle will bounce off at 180<sup>0</sup>. Now we need an objective for the game, something for your turtle to do and to score points for doing. For this game you are going to have your turtle chase and chomps space cabbages because we are making them green but you could choose a different colour and shape such as space cheese (e.g. yellow triangle)

Step 1.  Create the goal / objective
```python
player.penup()
Player.speed(0)

#create food
food = turtle.Turtle()
food.color("lightgreen")
food.shape("circle")
food.penup()
food.speed(0)
```
Step 2.  Save the game as kbgame4 and then run the module.
_*note: you should see the light green circle on the screen and can move around it_

Step 3.  Now we are going to set the cabbage in a position by typing:
```python
food.speed(0)
food.setposition(-100, 100) 
```

Step 4.  Save and run the module

Step 5.  Now we need to add collision detection as this will allow us to calculate when your turtle collides with (chomps) the space cabbage. We do this by using a bit of math to work out where the turtle and cabbage is and if they are touching and the distance between them is small. For the math nerds here we will use one of Pythagoras’s theories. To do that we need to import the math libraries at the top of our application:
```python
# Turtle Graphics Game – Space Turtle Chomp
import turtle
import math
```

Step 6.  So the math formula we use will take the x coordinate of the turtle subtracting from the x coordinate of the cabbage then squaring it and doing the same for the y coordinates for the turtle and cabbage then working out the square root. It’s OK not to completely understand (I’m not sure I do :-) ) but you need to type the following within your While Loop:
```python
    # Boundary Checking x coordinate
    if player.ycor() > 290 or player.ycor() < -290:
        player.right(180)

    # Collision checking
    d = math.sqrt(
            math.pow(player.xcor() - food.xcor(), 2)
            + math.pow(player.ycor() - food.ycor(),2))
    if d < 20:
        food.hideturtle()
```
So here we have that if the distance between the turtle and cabbage is less than 20 then we will hide the cabbage (food).

Step 7.  Save and run the module, move your turtle to collide with the cabbage. Now that works, it will be a fairly boring game just to hide the cabbage so to make it more interesting what we will do is once the turtle collides (chomps) the cabbage we move it to a random position. For this to work we first need to import the random library:
```python
# Turtle Graphics Game – Space Turtle Chomp
import turtle
import math
import random
```

Step 8.  Now you set the random position within the x and y coordinates:
```python
    # Collision checking
    d = math.sqrt(
        math.pow(player.xcor()-food.xcor(),2)
        + math.pow(player.ycor()-food.ycor(),2))
    if d < 20:
        food.setposition(random.randint(-290, 290), random.randint(-290, 290))
```

Step 9.  Save and run the module. We now have the basis of our game
_*note: we set the random position at -290 and 290 and not -300 and 300 so the cabbage will not appear on the border._

Step 10.  Now you can use the same random position option to randomise where the cabbage appears at the start of the game by replacing the food.setposition:
```python
food.setposition(random.randint(-290, 290), random.randint(-290, 290))
```
Step 11.  Save and Run the model

Your code should now look like this: [kbgame4.py](/src/kbgame4.py)

**Congratulations Module 4 Completed**