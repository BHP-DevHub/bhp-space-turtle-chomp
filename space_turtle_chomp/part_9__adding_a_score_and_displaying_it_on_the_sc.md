## Part 9 – Adding a score and displaying it on the screen {#part-9-adding-a-score-and-displaying-it-on-the-screen}

To make this more like a game you can add a score for each time your turtle chomps on a cabbage. To do this you create a new score variable by typing the following

Step 1.  Move to the #Create turtle section of your code and type the following:
```python
player.shape("turtle")
player.penup()
Player.speed(0)

# Create variable score
score = 0
```

Step 2.  Move to the bottom of your While Loop at the end of your collision checking section and type:
```python
    # Collision checking
    if isCollision(player, foods[count]):
        foods[count].setposition(random.randint(-290, 290), random.randint(-290, 290))
        foods[count].right(random.randint(0,360))
        winsound.PlaySound('chomp.wav', winsound.SND_ASYNC)
        score +=1
```
*note: this will calculate a score but you can’t see it on the screen

Step 3.  Now we add the score to the screen by re-using the mypen turtle and using it to write the score, you can do this by typing:
```python
    winsound.playSound('chomp.wav', winsound.SND_ASYNC)
    score +=1
    mypen.penup()
    mypen.hideturtle()
    mypen.setposition(-290, 310)
    scorestring ="Score: %s" % score
    mypen.write(scorestring, False, align='left', font=('Arial', 14, 'normal'))
```
So you have created a string that displays the score in the top left hand corner of your screen

Step 4.  Save your game as kbgame9 and run your module

What you should now see is that your score is in the top left hand corner of the screen but the number (1, 2, 3, 4 etc.) are writing on top of each other. You can fix this by delete the previous score before writing the new score.

Step 5.  Add the undo option to the mypen section:
```python
    mypen.undo
    mypen.penup()
    mypen.hideturtle()
    mypen.setposition(-290, 310)
    scorestring ="Score: %s" % score
    mypen.write(scorestring, False, align='left', font=('Arial', 14, 'normal'))
```

Step 6.  Save and Run your module

Your code should look like this: Mac/Linux [kbgame9.py](/src/kbgame9.py), Windows [kbgame9.py](/src/kbgame9_win.py)

**Congratulations Module 9 Completed**