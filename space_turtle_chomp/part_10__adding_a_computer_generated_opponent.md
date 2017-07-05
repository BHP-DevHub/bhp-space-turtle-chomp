## Part 10 – Adding a computer generated opponent {#part-10-adding-a-computer-generated-opponent}

In general games are more fun if you get to compete against an opponent, for Space Turtle Chomp this is very easy to do as we have already written all the code we just need to create an opponent section and cut and paste then modify our existing code.

Step 1.  First we need to create a new turtle object as the opponent, move just under \#Create player turtle and add:

```python
# Create player turtle
player = turtle.Turtle()
player.color('darkorange')
player.shape('turtle')
player.penup()
Player.speed(0)

# Create opponent turtle
comp = turtle.Turtle()
comp.color('red')
comp.shape('turtle')
comp.penup()
comp.setposition(random.randint(-290, 290), random.randint(-290, 290))
```

Step 2.  Save your game as kbgame10 and run your module

You now have a Red opponent space Turtle now you can make it move around the screen and add the boundary checking so it doesn’t run away. Move to your While Loop section and add the following:

```python
while True:
    player.forward(speed)
    comp.forward(12)

    # Boundary Player Checking x coordinate
    if player.xcor() > 290 or player.xcor() < -290:
        player.right(180)
        os.system('afplay bounce.mp3&')

    # Boundary Player Checking y coordinate
    if player.ycor() > 290 or player.ycor() < -290:
        player.right(180)
        os.system("afplay bounce.mp3&")

    # Boundary Comp Checking x coordinate
    if comp.xcor() > 290 or comp.xcor() < -290:
        comp.right(180)
        os.system('afplay bounce.mp3&')

    # Boundary Comp Checking y coordinate
    if comp.ycor() > 290 or comp.ycor() < -290:
        comp.right(180)
        os.system('afplay bounce.mp3&')
```

_\*note: you can make the comp.forward speed faster or slower by changing the number within the brackets_

Step 3.  Save and run your module

Now your opponent turtle is moving around the screen and bouncing of the walls, next we want to give them a score

Step 4.  Within the variable score section add:

```python
# Create variable score
score = 0
comp_score = 0
```

Step 5. Now you create your competition score just under your Create competition turtle

```py
# Create competition score
mypen2 = turtle.Turtle()
mypen2.color('red')
mypen2.hideturtle()
```

Step 6.  Now copy the player collision checking paste below and update as below:

```python
    # Collision checking
    if isCollision(player, foods[count]):
        foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
        foods[count].right(random.randint(0,360))
        winsound.playSound('chomp.wav', winsound.SND_ASYNC)
        score +=1
        mypen.penup()
        mypen.hideturtle()
        mypen.setposition(-290, 305)
        scorestring ="Score: %s" % score
        mypen.write(scorestring, False, align='left', font=('Arial', 14, 'normal'))

    # Comp Collision checking
    if isCollision(comp, foods[count]):
        foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
        foods[count].right(random.randint(0,360))
        winsound.playSound('chomp.wav', winsound.SND_ASYNC)
        comp_score+=1
        # Draw the Comp score on the screen
        mypen2.undo()
        mypen2.penup()
        mypen2.hideturtle()
        mypen2.setposition(200, 305)
        scorestring ="Score: %s" % comp_score
        mypen2.write(scorestring, False, align='left', font=('Arial', 14, 'normal'))
```

Step 7.  Save and run your module

Your code should look like this: Mac/Linux [kbgame10.py](/src/kbgame10.py), Windows [kbgame10.py](/src/kbgame10_win.py)

**Congratulations Module 10 Completed**

