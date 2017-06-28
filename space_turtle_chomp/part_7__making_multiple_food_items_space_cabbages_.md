## Part 7 – Making multiple food items (Space Cabbages) to chase {#part-7-making-multiple-food-items-space-cabbages-to-chase}

In this section you are going to develop a way of having multiple space cabbages (food) moving around the screen for your turtle to chomp. You are going to do this using the python functions of Lists and Loops

1.  1<sup>st</sup> we create the maximum number of cabbages and an empty list

| 27 | player.shape(&quot;turtle&quot;) |
| --- | --- |
| 28 | player.penup() |
| 29 | Player.speed(0) |
| 30 |  |
| 31 | #create food |
| 32 | maxFoods = 6 |
| 33 | foods = [] |
| 34 |  |

1.  Next you create a for loop using maxFoods as the range updating the code from this

| 31 | food = turtle.Turtle() |
| --- | --- |
| 32 | food.color(&quot;lightgreen&quot;) |
| 33 | food.shape(&quot;circle&quot;) |
| 34 | food.penup() |
| 35 | food.speed(0) |
| 36 |  |

To this

| 38 | for count in range(maxFoods): |
| --- | --- |
| 39 | foods.append (turtle.Turtle()) |
| 40 | foods[count].color(&quot;lightgreen&quot;) |
| 41 | foods[count].shape(&quot;circle&quot;) |
| 42 | foods[count].penup() |
| 43 | foods[count].speed(0) |
| 44 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 45 |  |

So we use the append function to add our maximum number of cabbages held in the list, so foods.[1] is a turtle object, foods.[2] is a turtle object etc. etc.

1.  Now you need to do the same thing for moving the turtle within the # Move Food around section by changing

| 79 | # Move food around |
| --- | --- |
| 80 | food.forward(3) |

To

| 79 | # Move food around |
| --- | --- |
|  | for count in range(maxFoods): |
|  | foods[count].forward(3) |
|  |  |

And then indent and change

| 80 | #Boundary Food Checking x coordinate |
| --- | --- |
| 81 | if food.xcor() &gt; 290 or food.xcor() &lt;-290: |
| 82 | food.right(180) |
| 83 |  |
| 84 | #Boundary Food Checking y coordinate |
| 85 | if food.ycor() &gt; 290 or food.ycor() &lt;-290: |
| 86 | food.right(180) |

To

| 80 | #Boundary Food Checking x coordinate |
| --- | --- |
| 81 | if foods[count].xcor() &gt; 290 or foods[count].xcor() &lt;-290: |
| 82 | foods[count].right(180) |
| 83 |  |
| 84 | #Boundary Food Checking y coordinate |
| 85 | if foods[count].ycor() &gt; 290 or foods[count].ycor() &lt;-290: |
| 86 | foods[count].right(180) |

1.  Now let’s move (cut and paste) your collision checking within move goal loop. Make sure you indent and then change food to foods[count]

| 90 | # Collision checking |
| --- | --- |
| 91 |  |
| 92 | if isCollision(player, food): |
| 93 | food.setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 94 | …….food.right(random.randint(0, 360)) |

| 90 | #Collision checking |
| --- | --- |
| 91 | if isCollision(player, foods[count]): |
| 92 | foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290)) |
| 93 | foods[count].right(random.randint(0,360)) |
| 94 |  |

1.  Save the game as kbgame7 and run your module

You now have multiple cabbages moving around your screen however the screen can start to look a bit jumpy, to fix this we can add the tracer function to the program. This tells the computer not to refresh the screen each time, this speeds up the animation.

1.  Add the tracer function by typing the following in the # Set up screen area

| 3 | #Set up screen |
| --- | --- |
| 4 | turtle.setup(650,650) |
| 5 | wn = turtle.Screen() |
| 6 | wn.bgcolor(&quot;navy&quot;) |
|  | wn.tracer(3) |

1.  Save and run your module

Congratulations Module 7 Completed