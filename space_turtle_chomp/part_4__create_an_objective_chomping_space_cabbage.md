## Part 4 – Create an objective (chomping space cabbage) and collision checking {#part-4-create-an-objective-chomping-space-cabbage-and-collision-checking}

OK so now you have your turtle that we can move around the screen and if we bump into any of the boarders your turtle will bounce off at 180<sup>0</sup>. Now we need an objective for the game, something for your turtle to do and to score point doing. For this game you are going to have your turtle chase and chomps space cabbages because we are making them green but you could choose a different colour and shape such as space cheese (e.g. yellow triangle)

1.  Create the goal / objective

| 27 | player.penup() |
| --- | --- |
| 28 | Player.speed(0) |
| 29 |  |
| 30 | #create food |
| 31 | food = turtle.Turtle() |
| 32 | food.color(&quot;lightgreen&quot;) |
| 33 | food.shape(&quot;circle&quot;) |
| 34 | food.penup() |
| 35 | food.speed(0) |
| 36 |  |

1.  Save the game as kbgame4 and then run the module.*note: you should see the light green circle on the screen and can move around it
2.  Now we are going to set the cabbage in a position by typing

| 35 | food.speed(0) |
| --- | --- |
| 36 | food.setposition(-100, 100) |

1.  Save and run the module
2.  Now we need to add collision detection as this will allow us to calculate when your turtle collides with (eats) your space cabbage. We do this by using a bit of math to work out where the turtle and cabbage is and if they are touching and the distance between them is small. For the math nerds here we will use one of Pythagoras’s theories. To do that we need to import the math libraries at the top of our application.

| 1 | #Turtle Graphics Game – Space Turtle Chomp |
| --- | --- |
| 2 | import turtle |
| 3 | Import math |

1.  So the math formula we use will take the x coordinate of the turtle subtracting from the x coordinate of the cabbage then squaring it and doing the same for the y coordinates for the turtle and cabbage then working out the square root. It’s OK not to completely understand (I’m not sure I do :-) ) but you need to type the following within your While Loop

| 60 | #Boundary Checking x coordinate |
| --- | --- |
| 61 | if player.ycor() &gt; 290 or player.ycor() &lt;-290: |
| 62 | player.right(180) |
| 63 |  |
| 64 | # Collision checking |
| 65 | d = math.sqrt(math.pow(player.xcor()-food.xcor(),2) + math.pow(player.ycor()-food.ycor(),2)) |
| 66 | if d &lt; 20: |
| 67 | food.hideturtle() |
| 68 |  |

So here we have that if the distance between the turtle and cabbage is less than 20 then we will hide the cabbage (food)

1.  Save and run the module, move your turtle to collide with the cabbageNow that works, it will be a fairly boring game just to hide the cabbage so to make it more interesting what we will do is once the turtle collides (eats) the cabbage we move it to a random position. For this to work we first need to import the random library.

| 1 | #Turtle Graphics Game – Space Turtle Chomp |
| --- | --- |
| 2 | import turtle |
| 3 | Import math |
| 4 | Import random |

1.  Now you set the random position within the x and y coordinates

| 64 | # Collision checking |
| --- | --- |
| 65 | d = math.sqrt(math.pow(player.xcor()-food.xcor(),2) + math.pow(player.ycor()-food.ycor(),2)) |
| 66 | if d &lt; 20: |
| 67 | food.setposition(random.randint(-290, 290), random.randint(-290, 290)) |

1.  Save and Run the modelWe now have the basis of our game*note: we set the random position at -290 and 290 and not -300 and 300 so the cabbage will not appear on the boarder
2.  Now you can use the same random position option to randomise where the cabbage appears at the start of the game by replacing the food.setposition

| 36 | food.setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| --- | --- |

1.  Save and Run the model

Congratulations Module 4 Completed