## Part 5 – Collision checking using a function {#part-5-collision-checking-using-a-function}

You have collision checking working but as we add more cabbages it make the code easier if you convert your existing code to a function

1.  To create as a function we will use the “isCollision to retrun a true or fales return, to do that type

| 49 | def increasespeed () |
| --- | --- |
| 50 | global speed |
| 51 | speed += 1 |
| 52 |  |
| 25 | def isCollision(t1, t2): |
| 26 | d = math.sqrt(math.pow(t1.xcor()-t2.xcor(),2) + math.pow(t1.ycor()-t2.ycor(),2)) |
| 27 | if d &lt; 20: |
| 28 | return True |
| 29 | else: |
| 30 | return False |

So your function uses t1 and t2 as generic terms instead of turtle and food using the same collision formula as before with an if statement that returns a True vales if they are in the same location (collide) and a False value when they don’t

1.  Now you update the While Loop collision section with

| 64 | # Collision checking |
| --- | --- |
| 65 |  |
| 66 | if isCollision(player, food): |
| 67 | food.setposition(random.randint(-290, 290), random.randint(-290, 290)) |

1.  Save your games as kbgame5 and run your module

Congratulations Module 5 Completed