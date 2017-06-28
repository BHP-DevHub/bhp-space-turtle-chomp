## Part 2 – Keyboard Bindings and Turning the Turtle {#part-2-keyboard-bindings-and-turning-the-turtle}

In part 2 we will assign keys to control the turtle and help it move left, right and faster

1.  A good habit to get into with any coding is to regularly save versions of your code as you make changes as this allows you to either re-use code for other programs or roll back to a working version if something goes wrong. So click File --&gt; Save As and save the file as kbgame2
2.  We need to set keyboard bindings that tell the computer that when I push a certain key to call a certain function. For this to work we need to set the computer to listen for keyboard strokes by typing

| 12 | speed = 1: |
| --- | --- |
| 13 |  |
| 14 | #Set keyboard binding |
| 15 | turtle.listen() |
| 16 | turtle.onkey(turnleft, &quot;Left&quot;) |
| 17 | turtle.onkey(turnright, &quot;Right&quot;) |
| 18 | turtle.onkey(increasespeed, &quot;Up&quot;) |
| 19 |  |
| 20 | While True |

We use the turtle.onkey method will set the computer to listen for a certain key and when that is pressed it will run the assigned function.so when the left arrow key is pressed it will call the function called turnleft._*note: that this new piece of code sits between setting the speed (line 12) and the start of the while loop (line 20). In python where the code sits is very important_

1.  The next step is to write the turnleft, turnright and increassespeed functions.

| 12 | speed = 1: |
| --- | --- |
| 13 |  |
| 14 | #Define functions |
| 15 | def turnleft(): |
| 16 | player.left(30) |
| 17 |  |
| 18 | def turnright(): |
| 19 | player.right(30) |
| 20 |  |
| 21 | def increasespeed () |
| 22 | global speed |
| 23 | speed += 1 |
| 24 |  |
| 25 |  |
| 26 | #Set keyboard binding |

player.left and player.right are set to turn at 30<sup>o </sup> when the left and right arrow keys are pushed (remember to push and let go) global speed is a Global function and we have set that everytime the up arrow key is pushed the turtle increases its speed by 1\.

1.  Save the file by selecting File --&gt; Save and run your updated program by pressing F5 and then click on your turtle screen with the mouse and use the left and right arrow keys to move your turtle and the up arrow to increase its speed
2.  Close the Turtle and Python Shell windows
3.  You might see that the turtle icon jumps a bit when you press the arrow keys, this can be fixed very easily by adding the player speed variable

| 6 | #Create player turtle |
| --- | --- |
| 7 | player = turtle.Turtle() |
| 8 | player.color(&quot;darkorange&quot;) |
| 9 | player.shape(&quot;turtle&quot;) |
| 10 | player.penup() |
| 11 | Player.speed(0) |

_*note: 0 is the fasted animation speed._

1.  Save and Run your module again try moving the turtle icon now and then close the Turtle and Python Shell windows

Congratulations Module 2 Completed