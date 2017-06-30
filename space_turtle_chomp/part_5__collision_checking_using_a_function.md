## Part 5 – Collision checking using a function {#part-5-collision-checking-using-a-function}

You have collision checking working but as we add more cabbages it make the code easier if you convert your existing code to a function

Step 1.  To create as a function we will use the “isCollision to retrun a true or fales return, to do that type:
```python
def increasespeed ()
    global speed
    speed += 1

def isCollision(t1, t2):
       d = math.sqrt(
               math.pow(t1.xcor()-t2.xcor(),2)
               + math.pow(t1.ycor()-t2.ycor(),2))
       if d < 20:
           return True
       else:
           return False

```
So your function uses t1 and t2 as generic terms instead of turtle and food using the same collision formula as before with an if statement that returns a True vales if they are in the same location (collide) and a False value when they don’t.

Step 2.  Now you update the While Loop collision section with
```python
# Collision checking
if isCollision(player, food):
    food.setposition(random.randint(-290, 290), random.randint(-290, 290))
```

Step 3.  Save your game as kbgame5 and run your module.

Your code should now look like this: [kbgame5.py](/src/kbgame5.py)

**Congratulations Module 5 Completed**