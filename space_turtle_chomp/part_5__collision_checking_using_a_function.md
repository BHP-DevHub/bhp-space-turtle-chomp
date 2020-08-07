## Part 5 – Collision checking using a function {#part-5-collision-checking-using-a-function}

You have collision checking working but as we add more cabbages it makes the code easier if you convert your existing collision code to a function

Step 1. To convert your collision code into a function we will first add a new function. This code will go at the end of the #Define functions section, and use "isCollision" to return a True or False:

```python
def isCollision(t1, t2):
       d = math.sqrt(math.pow(t1.xcor()-t2.xcor(),2) + math.pow(t1.ycor()-t2.ycor(),2))
       if d < 20:
           return True
       else:
           return False
```

So your function uses t1 and t2 as generic terms instead of turtle and food and uses the same collision formula as before with an if statement that returns a True vales if they are in the same location \(collide\) and a False value when they don’t.

Step 2.  Now you need to update the code within the while True loop \# Collision checking section to look like:

```python
# Collision checking
if isCollision(player, food):
    food.setposition(random.randint(-290, 290), random.randint(-290, 290))
```

Step 3.  Save your game as kbgame5 and run your module.

Your code should now look like this: [kbgame5.py](/src/kbgame5.py)

**Congratulations Module 5 Completed**

