## Part 2 – Keyboard Bindings and Turning the Turtle {#part-2-keyboard-bindings-and-turning-the-turtle}

In part 2 we will assign keys to control the turtle and help it move left, right and faster

1.  A good habit to get into with any coding is to regularly save versions of your code as you make changes as this allows you to either re-use code for other programs or roll back to a working version if something goes wrong. So click File --&gt; Save As and save the file as kbgame2
2.  We need to set keyboard bindings that tell the computer that when I push a certain key to call a certain function. For this to work we need to set the computer to listen for keyboard strokes by typing:

```python
speed = 1
# Set keyboard binding
turtle.listen()
turtle.onkey(turnleft, &quot;Left&quot;)
turtle.onkey(turnright, &quot;Right&quot;)
turtle.onkey(increasespeed, &quot;Up&quot;)
while True:
```

We use the turtle.onkey method will set the computer to listen for a certain key and when that is pressed it will run the assigned function.so when the left arrow key is pressed it will call the function called turnleft._*note: that this new piece of code sits between setting the speed (line 12) and the start of the while loop (line 20). In python where the code sits is very important_

1.  The next step is to write the turn_left, turn_right and increase_speed functions.

```python
speed = 1

# Define functions
def turn_left():
    player.left(30)

def turn_right():
    player.right(30)

def increase_speed():
    global speed
    speed += 1

# Set keyboard binding
```

player.left and player.right are set to turn at 30<sup>o </sup> when the left and right arrow keys are pushed (remember to push and let go) global speed is a global function and we have set that everytime the up arrow key is pushed the turtle increases its speed by 1.

1.  Save the file by selecting File --&gt; Save and run your updated program by pressing F5 and then click on your turtle screen with the mouse and use the left and right arrow keys to move your turtle and the up arrow to increase its speed
2.  Close the Turtle and Python Shell windows
3.  You might see that the turtle icon jumps a bit when you press the arrow keys, this can be fixed very easily by adding the player speed variable

```python
# Create player turtle
player = turtle.Turtle()
player.color('darkorange')
player.shape('turtle')
player.penup()
Player.speed(0)
```

_*note: 0 is the fasted animation speed._

1.  Save and Run your module again try moving the turtle icon now and then close the Turtle and Python Shell windows

Your code should now look like this: [kbgame2.py](/src/kbgame2.py)

**Congratulations Module 2 Completed**