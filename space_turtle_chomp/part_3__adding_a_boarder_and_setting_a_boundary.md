## Part 3 – Adding a border and setting a boundary {#part-3-adding-a-boarder-and-setting-a-boundary}

Currently with our turtle game you can move your player turtle of the screen which we don’t want to do son in this module we are going to draw and boarder and then set boundaries so your player turtle can not move of the screen.

1. Use Save As to save your module as kbgame3
2. Move to the top of your code just under the \#Set up Screen and create and new turtle called border

| 8 | wn.bgcolor\("Navy"\): |
| --- | --- |
| 9 |  |
| 10 | \#Draw boarder |
| 11 | mypen = turtle.Turtle\(\) |
| 12 | mypen.penup\(\) |
| 13 | mypen.setposition\(-300,-300\) |
| 14 | mypen.pendown\(\) |
| 15 | mypen.pensize\(3\) |
| 16 | for side in range\(4\): |
| 17 | mypen.forward\(600\) |
| 18 | mypen.left\(90\) |
| 19 | mypen.hideturtle\(\) |
| 20 |  |
| 21 | \#Create player turtle |
|  |  |

setposition places the mypen turtle in the bottom left hand corner of your screenpendown gets your mypen turtle ready to drawthe for side in range \(4\) tells your mypen turtle to draw four sides using a simle loop of draw forward for 600 points then turn left repeating four times.

1. Save and Run your module._\*note: while there is now a boarder your player turtle can still go off screen, this is because we have not set boundaries yet._

Now we have to do something called boundary checking and what this will do is check the location of our turtle and basically on the left it is lower than -300 and on the right it is greater than +300 we have hit the boarder \(x Axis\) and the same for Top greater than +300 and Bottom lower than -300 \(y Axis\) we have hit the boarder. What we then need to do is choose what we want to happen when this occurs, for this game we are going to bounce of the boarder wall at 180 degrees.

1. As we need this to happen every time during the game we need the code to be written within the while True loop

| 52 | while True: |
| --- | --- |
| 53 |  |
| 54 | player.forward\(speed\) |
| 55 |  |
| 56 | \#Boundary Checking x coordinate |
| 57 | if player.xcor\(\) &gt; 290 or player.xcor\(\) &lt;-290:: |
| 58 | player.right\(180\) |
| 59 |  |
| 60 | \#Boundary Checking y coordinate |
| 61 | if player.ycor\(\) &gt; 290 or player.ycor\(\) &lt;-290: |
| 62 | player.right\(180\) |

\*note we have set the boundary at 290 and -290 so that the turtle bounces when the front of the turtle hits the boundary and not the middle

1. Save and then Run your module

Congratulations Module 3 Completed

