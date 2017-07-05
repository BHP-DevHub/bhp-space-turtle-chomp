## Part 6 – Moving and setting boundary checking for the food (cabbage) {#part-6-moving-and-setting-boundary-checking-for-the-food-cabbage}

So what you will do next is make the food move around the screen, this is fairly easy to do by using the forward option.

Step 1.  Within the While Loop add the following code:
```python
    # Boundary Checking y coordinate
    if player.ycor() > 290 or player.ycor() < -290:
        player.right(180)

    # Move food around
    food.forward(1)
```

Step 2.  Save your game as kbgame6 and run the module

Step 3.  Now your cabbage moves across the screen but at the moment it always moves to the right, so let make the game more interesting by using the random function again by typing:
```python
# Collision checking
if isCollision(player, food):
    food.setposition(random.randint(-290, 290), random.randint(-290, 290))
    food.right(random.randint(0, 360))
```

Step 4.  The food is moving rather slow so let’s speed it up by changing the forward speed to 3 by typing:
```python
# Move food around
    food.forward(3)
```

Step 5.  Save and run your module, have a play with different speeds. Your food is now moving around the screen in random direction the only problem we have is that it can move of the screen. This is an easy fix as you can cut and paste the same code you wrote for your turtle for border checking and modify it for the food.

Step 6.  Add the following code to your application, you can cut and paste the code above
```python
    # Boundary Checking x coordinate
    if player.xcor() > 290 or player.xcor() < -290::
        player.right(180)

    # Boundary Checking y coordinate
    if player.ycor() > 290 or player.ycor() < -290:
        player.right(180)

    # Boundary Food Checking x coordinate
    if food.xcor() > 290 or food.xcor() < -290:
        food.right(180)

    # Boundary Food Checking y coordinate
    if food.ycor() > 290 or food.ycor() < -290:
        food.right(180) 
```
Now when your space cabbage hits the boundary it will bounce of the wall at 180<sup>0</sup> just like your turtle

Step 7.  Save and run your module

Your code should now look like this: [kbgame6.py](/src/kbgame6.py)

**Congratulations Module 6 Completed**