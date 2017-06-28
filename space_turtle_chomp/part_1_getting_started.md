## Part 1 – Getting Started {#part-1-getting-started}

We will start of today creating a simple Python game using Python Turtle Graphics. Turtle Graphics a prebuilt set of python instructions that allow you to create and move characters around the screen allowing you to draw pictures, logos and create simple animations or games.

1.  If not already open please open your Python IDE application You should see you Shell Script window
2.  Select File --&gt; New FileYou should see your program window
3.  As it is a great idea to save your project at the beginning of any new development, select File --&gt; Save and name kbgame1

```python
# Turtle Graphics Game – Space Turtle Chomp
```
First thing we should always do as a developer is leave a comment explaining what the program does at the top of the screen. Write the below on the top line

Next we need to Import the Turtle libraries and set up the screen, we do this by typing:

```python
import turtle

# Set up screen
turtle.setup(650,650)
wn = turtle.Screen()
wn.bgcolor('navy')
```
turtle.setup sets the size of the Turtle game window (it’s not nesesary but helps when using different screen sizes). wn is the name we are calling the screen (as we learnt in the Python introduction all variables need a name) bgcolor allows us to set the background colour There are lots of colours to choose from see [color chart](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/color_chart.jpg) for options 

_*note the American spelling of color, this is something to watch out for when programing_. As always it is good programming to leave a comment (#) before your code so you can remember what it does

Next we create our 1<sup>st</sup> Turtle character, we do this by typing

```python
# Create player turtle
player = turtle.Turtle()
player.color('darkorange')
player.shape('turtle')
player.penup()
```
So we create a new turtle variable called player then use the inbuilt turtle attributes to help set it up, player.color (again we can select a different colour from the [color chart](https://mysite.bhpbilliton.com/personal/kieran_mccluskey_bhpbilliton_com/Documents/01%20Dev%20Platform/14%20Culture/Perth%20web%20Girls/Python%20Game/kbgame/color_chart.jpg)). player.shape selects the shape (you can also use circle, arrow, square and classic). Penup means that the turtle shape won’t leave a line went it moves (think of a pen in your hand, penup() you don’t draw, pendown() you do draw.

Now we set the speed our turtle will move across the screen:

```python
# Set speed variable
speed = 1
```
Finally we need the Turtle to move and the easiest way to do this is by setting a while loop:

```python
while True:
    player.forward(speed)
```
This will now continue to move your turtle forward across the screen at a speed of 1.

*note the indent of the player.forward… this needs to be there for the code to work {#this-will-now-continue-to-move-your-turtle-forward-across-the-screen-at-a-speed-of-1-note-the-indent-of-the-player-forward-this-needs-to-be-there-for-the-code-to-work}

Now all we need to do is save our code, we can do this by select File --&gt; Save (Ctrl S on Windows or Cmd S on Mac).Then run the module by selecting Run --&gt; Run Module (or pressing F5)

You should see two windows open up a Python Shell window that will have “Python 3.6.1 (v3.6.1:69c0db5, Mar 21 2017, 17:54:52) [MSC v.1900 32 bit (Intel)]…” or something similar written on it and your Turtle window with a Navy background and Dark Orange turtle moving across the screen. Close both the shell and turtle window to return to your programming code.

Congratulations Module 1 Completed